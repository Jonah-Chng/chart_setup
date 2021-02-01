# setup

To reduce the pain of losing everything and trying to reset everything up again. Here is the list of this I run to setup my work environment:

sudo apt update
sudo apt install git python3-pip

# rmf_demos dependencies
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
sudo apt update
sudo apt install -y wget
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
wget https://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
sudo apt update && sudo apt install \
  git cmake python3-vcstool curl \
  qt5-default \
  python3-shapely python3-yaml python3-requests \
  -y
sudo apt-get install python3-colcon*

## For rmf_panel
sudo apt install npm
python3 -m pip install Flask flask-socketio flask-cors
cd ~/rmf_demos_ws

### change the npm prefix according to the path to "rmf_demo_panel/static/"
npm install --prefix src/rmf/rmf_demos/rmf_demo_panel/rmf_demo_panel/static/
npm run build --prefix src/rmf/rmf_demos/rmf_demo_panel/rmf_demo_panel/static/

colcon build --packages-select rmf_demo_panel

# For wasg-register
pip3 install pycryptodome
pip3 install requests
python3 -m pip install Flask flask-socketio flask-cors

# Repos
https://github.com/osrf/rmf_demos/

# TODO
Docker
