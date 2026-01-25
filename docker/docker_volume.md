Why we need Docker Volumes..?

Because the first thing we need to know about the container is , the containers are ephemeral in nature so the life span is short . so when they stop or deleted the data is lost which is not a good so voulmes are introduced where to persist the data even though container stops
     1)volumes keep data safe outside the container
     2)containers can be created without lossing data

Docker provides 2 ways:
     
     1)Bind mounts: Bind mounts map a specific folder on the host machine directly into a container, means changes on host immediately appear in container  and container changes immediately appear on host
         
         They are mainly  used for local development , live code changes 


    2)Volumens :Docker volumes are docker managed storage used to persist the container data.
        
        Here both the mounts and volumes are used to solve the same problem but the volumes are better than mounts where
          
          1)volumes are managed by docker where as mounts not
          2)volumes are not host dependency but mounts are dependent on host
          3) the most important the volumes are portable i mean we can attach the volume of c1 container to c2 , But in the mouts u can attach the mounts only they should have the same host

     ##commands

     1) to create a volume
           
           # docker volume create  <Name>

    2) to view the volumes created 

           # docker volume ls

    3)To attach the volume to the docker container

          # docker run -d --name <container_name> -v <volume_name>:/app ubuntu

        ## using the mount also we can attach the volume

          # docker run -it --name mycontainer --mount source=<volume_name>,target=/app ubuntu


    ############
        
        1) You cannt attach a volume to a running container

        2) Volume must be attached at container creation time


        To check whether a volume is attached to your container or not u  can check it by inspecting the docker using the # docker inspect <container_id/name>

   #############

    4)To inspect the docker or to know the details of the volume i mean when it was created and mount point and where it was stored 

         # docker volume inspect <name>


    5) To delete a volume 
          
          # docker volume rm <name>

