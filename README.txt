*If /tmp folder permission denied*
docker exec -it lemp_nginx sh -c "chmod 777 -R /tmp"

*Use port 80 from lemp_nginx to php*
docker exec -it lemp_php sh -c "socat TCP-LISTEN:80,fork TCP:10.10.100.10:80 &"
