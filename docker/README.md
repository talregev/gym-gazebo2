# gym-gazebo2 Docker container usage

## Build the container

```shell
git clone docker gym-gazebo-ros2
cd gym-gazebo-ros2/docker
mkdir src
cp ../provision/mara.repos .
vcs import src < mara.repos
vcs import src < missing-repos.repos
git clone https://github.com/erlerobot/baselines
git clone https://github.com/erlerobot/gym-gazebo-ros2
docker build -t gg2 .
```

## Run the container

```shell
docker rm gg2 || true && docker run -it --name=gg2 -h gym-gazebo2 gg2
```

## Launch gzclient (GUI)
If you are already running the simulation in the default port, you can access the visual interface the following way:
```shell
cd gym-gazebo-ros2/docker
sh gzclient.sh
```