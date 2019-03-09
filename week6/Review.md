## Review

#### ### # Part 3：Docker Service
##### ## Prerequisites
- Install Docker version 1.13 or higher.
- Get Docker Compose. On Docker for Mac and Docker for Windows it's pre-installed, so you're good-to-go.On Linux system you need to install it directly. On pre Windows 10 system without Hyper-V, use Docker Toolbox.
- Read the orientation in Part 1.
- Learn how to create containers in Part 2.
- Make sure you have published the "friendlyhello" image you created by pushing it to a registry. We use that shared image here.
- Be sure your image works as a deployed container. Run this command, slotting in your info for "username", "repo" and "tag:docker run -p 4000:80 username/repo:tag", then visit http://ipaddress:4000/ .

##### ## Introduction
In part 3, we scale our application and enable load-balancing. 
To do this,we must go one level up in the hierarchy of a distributed application: the service
1. Stack
1. Services（you are here）
1. Container（covered in part 2）

##### ## About services
In a distributed application, different pieces of the app are called "services",For example, if you imagine a video sharing site
it probably includes a service for storing application data in a database,a service for video transcoding in the background after a user uploads something, a service for the front-end, and so on.

Services are really just "containers in production.", A service only runs one image, but it codifies the way that image runs--what ports it should use, how many replicas of the container should run so the service has the capacity it needs, and so on. Scaling a service changes the number of container instances running that piece of software, assigning more computing resources to the service in the process. Luckily it's very easy to define, run, and scale services with the Docker platform -- just write a "docker-compose.yml" file