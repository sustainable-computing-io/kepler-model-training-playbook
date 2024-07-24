# kepler-model-training-playbook

1. Copy `kepler-ci-key.pem` to current directory for spot machine ssh.
2. Modify AWS region and append secrets in `group_vars/all.yml`.
    ```
    access_key: 
    secret_key: 
    ```
3. Modify instance type list in `group_vars/local.yml`.
4. Run.
    ```
    ansible-playbook -i hosts.ini ec_spot.yml
    ```

## Collection status

[instance list script](https://gist.github.com/rootfs/49855d0c75ef8a27e494eda6eb928aab)

- :white_check_mark: : collected
- :x: : not available
- empty : not collected yet


Profile|Spot Price|v0.7.8|v0.7.11
---|---|---|---
r6a.metal| 2.288300 | :x: (AMD)
r6in.metal| 3.620800| :x: (AMD)
m7i.metal-24xl| 1.295600|:white_check_mark:|:white_check_mark: 
r7i.metal-48xl| 3.290300
m5d.metal| 2.109100
i4i.metal| 2.326700
c7a.metal-48xl| 2.770700
m6a.metal| 1.658900
g4dn.metal| 3.673600
r7iz.metal-16xl| 1.456300
m5.metal| 1.747800||:white_check_mark:
r5b.metal| 2.165300
c7i.metal-24xl| 1.224100
x2iedn.metal| 2.667600
m6i.metal| 2.178600
m6in.metal| 2.280400
m5n.metal| 1.522600
r7i.metal-24xl| 1.839900
r5dn.metal| 2.734300
c6a.metal| 1.629900
x2idn.metal| 1.333800
r5.metal| 2.032400||:white_check_mark: 
c5.metal| 1.447500||:white_check_mark: 
c6id.metal| 1.968700
c5n.metal| 1.216100
m6idn.metal| 2.488400
c7i.metal-48xl| 1.834300
r7a.metal-48xl| 3.507200
z1d.metal| 0.629400 | :x:
m5zn.metal| 0.536000 | :white_check_mark:|:white_check_mark: 
m5dn.metal| 1.351600
m6id.metal| 2.385700
r6i.metal| 2.780000
r5d.metal| 2.222400
r6id.metal| 2.155300
c6i.metal| 2.027300
r6idn.metal| 3.381500| :x: (AMD)
r7iz.metal-32xl| 2.962700
c5d.metal| 1.562000 | :white_check_mark: 
i3en.metal| 1.176300 | :white_check_mark: 
m7i.metal-48xl| 2.556500 | 
m7a.metal-48xl| 2.225700
i3.metal| 0.670800 | :white_check_mark:|:white_check_mark:
r5n.metal| 2.291800
c6in.metal| 1.943700