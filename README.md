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
localhost:5432

