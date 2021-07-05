## Solution to run csvserver app

- Write a shell script `gencsv` to generate csv content and write it to `inputFile` file
- Add a docker-compose.yaml file
- Copy inputFile to inputdata at `/csvserver/inputdata` by mounting it as a volume
- Add services for `csvapp` and `prometheus`
- Copy `prometheus` config to `/etc/prometheus/` directory by mounting it as a volume
- Run `docker-compose up` (make sure to run it in the directory where docker-compose.yaml is available)
- In another tab, open project directory and run the curl `curl -o ./part-1-output http://localhost:9393/raw`
- in the same directory, run docker logs command to get csvapp container's logs 
`docker logs [container_id] >& part-1-logs`
- Run curl to fetch prometheus metrics and filter metrics for the app csvserver and write to a file
- Run the container using `docker run` command by providig the same option given in docker-compose.yaml file and write the command to `part-1-cmd` file
