Install

1 - docker pull osrm/osrm-backend:latest
2 - cd osrm_data 
3 - wget http://download.geofabrik.de/asia/iran-latest.osm.pbf
4 - docker run -t -v "${PWD}:/data" osrm/osrm-backend:latest osrm-extract -p /opt/car.lua /data/iran-latest.osm.pbf
5 - docker run -t -v "${PWD}:/data" osrm/osrm-backend:latest osrm-partition /data/iran-latest.osrm
6 - docker run -t -v "${PWD}:/data" osrm/osrm-backend:latest osrm-customize /data/iran-latest.osrm 
7 - docker compose up -d

note : It may take up to half an hour to execute the bill nominatim service
-----
Update

docker exec -it nominatim sudo -u nominatim nominatim replication --project-dir /nominatim
sudo -u nominatim nominatim replication --project-dir /nominatim


