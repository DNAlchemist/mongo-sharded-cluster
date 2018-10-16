This project involves creating a new sharded cluster that consists a two instances of mongos, the config server replica set, and two shard replica sets.
    
    export DATA_DIR=$PWD
    docker-compose up -d

    # Check all containers is up to work. Otherwise, rerun `docker-compose up -d`.
    # Despite the dependence between the containers, the first container may simply
    # not be able to fully start the service

    # Initialize the cluster
    ./init

    # To access to the cluster through the balancer
    docker exec -it mongos1 mongo

    # To access on of the shards directly
    docker exec -it mongors1n1 mongo
