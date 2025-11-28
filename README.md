docker volume create osm-data
docker run  --rm  -v "${PWD}/bulgaria-latest.osm.pbf:/data/region.osm.pbf"  -v osm-data:/data/database/  overv/openstreetmap-tile-server import
docker run -p 8080:80   -p 5434:5432 -v osm-data:/data/database/ -e ALLOW_CORS=enabled --name osm-server -d overv/openstreetmap-tile-server run 

#echo "Test tile server"
#curl -k -L --output tile-3005.png "http://localhost:8080/tile/13/4731/3005.png"


Windows 11 / Docker Desktop 
1.
docker volume create osm-data
2.
docker run --rm -v osm-data:/data/database -v C:\Users\User\Desktop\docker\bulgaria-251127.osm.pbf:/data/region.osm.pbf overv/openstreetmap-tile-server import
3.
docker run -p 8080:80   -p 5434:5432 -v osm-data:/data/database/ -e ALLOW_CORS=enabled --name osm-server -d overv/openstreetmap-tile-server run 
4. java MiniStaticServer
