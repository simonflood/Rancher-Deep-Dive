```
                                    +---------+
                                    |End users|
                                    +----+----+
                                         |
                            +------------v------------+
                            | External Load Balancer  |
                            | TCP or HTTP Mode        |
                            | Ports: 80 & 443         |
           +----------------+------------+------------+--------------+
           |                             |                           |
+----------v--------------+ +------------v------------+ +------------v------------+
|RKE2 Work01              | |RKE2 Work02              | |RKE2 Work  N             |
+-------------------------+ +-------------------------+ +-------------------------+
|User application pods    | |User application pods    | |User application pods    |
|                         | |                         | |                         |
|                         | |                         | |                         |
|                         | |                         | |                         |
|                         | |                         | |                         |
+-------------------------+ +-------------------------+ +-------------------------+
|Ingress-Nginx-Controller | |Ingress-Nginx-Controller | |Ingress-Nginx-Controller |
+-------------------------+ +-------------------------+ +-------------------------+
|Longhorn                 | |Longhorn                 | |Longhorn                 |
+-------------------------+ +-------------------------+ +-------------------------+
|Worker                   | |Worker                   | |Worker                   |
+-------------------------+ +-------------------------+ +-------------------------+

+-------------------------+ +-------------------------+ +-------------------------+
|RKE Master 01            | |RKE Master 02            | |RKE Master 03            |
+-------------------------+ +-------------------------+ +-------------------------+
|Master                   | |Master                   | |Master                   |
+-----------^-------------+ +------------^------------+ +-------------^-----------+
            |                            |                            |
            +---------------+------------+------------+---------------+
                            |External Load Balancer   |
                            |           or            |
                            |Round-robin DNS          |
                            |Ports: 9345 & 6443 TCP   | 
                            +-------------------------+
```