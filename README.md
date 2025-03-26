# Datazoomcamp_HW1

Question 1. Understanding docker first run

--> Option 1
docker run -it --entrypoint=bash python:3.12.8
Package Version
------- -------
pip     24.3.1

--> Option 2
- create a dockerfile (ex:Dockerfile.HW1) with following script inside
FROM python:3.12.8
ENTRYPOINT [ "bash" ]
- within a CLI, run "docker build -t image_name:version -f Dockerfile.HW1 ."
- run: "docker run -it image_name:version"
- run: pip --version

Question 2. Understanding Docker networking and docker-compose
postgres:5432

Prepare Postgres
1- Launch Docker
2- CLI: docker run hello-world 
1- docker build -t homework:moduleone -f Dockerfile.HW1 . (build an image)
4- docker run -it homework:moduleone (build a container)
5- docker-compose -f docker-compose_HW1.yaml up (run docker compose)
6- run in CLI
python HW_Mod1.py \
   --user=root \
   --password=root \
   --host=localhost \
   --port=5432 \
   --db=taxi \
   --table_name=taxi_zone 

python HW_Mod1.py \
   --user=root \
   --password=root \
   --host=localhost \
   --port=5432 \
   --db=taxi \
   --table_name=green_taxi

7- launch the pgAdmin on the localhost and visualize the tables 

  
Question 3. Trip Segmentation Count
  ANS: 5 (476386)

Question 4. Longest trip for each day
  df_green_taxi[df_green_taxi['trip_distance'] == df_green_taxi['trip_distance'].max()].lpep_pickup_datetime
  2019-10-31

Question 5
# Merging the two dataframes
df=df_green_taxi.merge(df_taxi_zone, left_on='PULocationID', right_on='LocationID', how='left')
df[(df['total_amount'] > 800) & (df['lpep_pickup_datetime'] < '2019-10-18 00:00:00')]['Zone'].head(1)
ANS: Queensbridge/Ravenswood

Question 6. Largest tip
East Harlem North

Terraform
Downloading the provider plugins and setting up backend,

Question 7. Terraform Workflow

1- Downloading the provider plugins and setting up backend,
2- Generating proposed changes and auto-executing the plan
3- Remove all resources managed by terraform`

terraform init, terraform apply -auto-approve, terraform destroy



