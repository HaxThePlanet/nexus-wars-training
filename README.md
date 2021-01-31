
# Forked From
https://github.com/chris-chris/pysc2-examples

# Nexus wars map install

Put nw.SC2Map in repo \mini_maps here:

```shell
C:\Program Files (x86)\StarCraft II\Maps\Melee
```

# python --version

```shell
Python 3.6.8
```


# Pip list

```shell
 pip list
Package                       Version
----------------------------- -------------
absl-py                       0.11.0
aiohttp                       3.7.3
astor                         0.8.1
astunparse                    1.6.3
async-timeout                 3.0.1
attrs                         20.3.0
baselines                     0.1.6
bleach                        1.5.0
cachetools                    4.2.0
calamari-ocr                  1.0.5
certifi                       2020.12.5
chardet                       3.0.4
click                         7.1.2
cloudpickle                   1.2.2
cycler                        0.10.0
decorator                     4.4.2
deepdiff                      5.2.2
dill                          0.3.3
edit-distance                 1.0.4
enum34                        1.1.10
flatbuffers                   1.12
future                        0.18.2
futures                       3.1.1
gast                          0.3.3
google-auth                   1.24.0
google-auth-oauthlib          0.4.2
google-pasta                  0.2.0
grpcio                        1.32.0
gym                           0.15.7
h5py                          2.10.0
html5lib                      0.9999999
idna                          2.10
idna-ssl                      1.1.0
imageio                       2.9.0
importlib-metadata            3.4.0
joblib                        1.0.0
Keras-Preprocessing           1.1.2
kiwisolver                    1.3.1
lxml                          4.6.2
Markdown                      3.3.3
matplotlib                    3.3.4
mock                          4.0.3
mpyq                          0.2.5
multidict                     5.1.0
networkx                      2.5
nsml-StarCraft2-MineralShards 0.1
numpy                         1.19.5
oauthlib                      3.1.0
opencv-python                 4.5.1.48
opt-einsum                    3.3.0
ordered-set                   4.0.2
pandas                        0.25.3
Pillow                        7.2.0
pip                           21.0.1
portpicker                    1.3.1
prettytable                   2.0.0
protobuf                      3.14.0
pyasn1                        0.4.8
pyasn1-modules                0.2.8
pygame                        2.0.1
pyglet                        1.5.0
pyparsing                     2.4.7
PySC2                         3.0.0
python-bidi                   0.4.2
python-dateutil               2.8.1
pytz                          2020.5
PyWavelets                    1.1.1
requests                      2.25.1
requests-oauthlib             1.3.0
rsa                           4.7
s2clientprotocol              5.0.5.82893.0
s2protocol                    5.0.5.82893.0
sc2-env                       0.11.1.2
scikit-image                  0.17.2
scipy                         1.5.4
setuptools                    39.1.0
six                           1.15.0
sk-video                      1.1.10
tensorboard                   1.9.0
tensorboard-plugin-wit        1.8.0
tensorflow                    1.9.0
tensorflow-estimator          2.4.0
tensorflow-gpu                1.9.0
tensorflow-tensorboard        0.4.0
termcolor                     1.1.0
tifffile                      2020.9.3
tqdm                          4.56.0
typing-extensions             3.7.4.3
urllib3                       1.26.2
wcwidth                       0.2.5
websocket-client              0.57.0
Werkzeug                      1.0.1
wheel                         0.36.2
whichcraft                    0.6.1
wrapt                         1.12.1
XlsxWriter                    1.3.7
yarl                          1.6.3
zipp                          3.4.0
```

#Run it
```shell
python train_nexus_wars.py --map=nw --algorithm=deepq --prioritized=True --dueling=True --timesteps=2000000 --exploration_fraction=0.2
```


# StartCraft II Reinforcement Learning Examples

This example program was built on 
- pysc2 (Deepmind) [https://github.com/deepmind/pysc2]
- baselines (OpenAI) [https://github.com/openai/baselines]
- s2client-proto (Blizzard) [https://github.com/Blizzard/s2client-proto]
- Tensorflow 1.3 (Google) [https://github.com/tensorflow/tensorflow]

# Current examples

## Minimaps
- CollectMineralShards with Deep Q Network

![CollectMineralShards](https://media.giphy.com/media/UrgVK9TFfv2AE/giphy.gif "Collect Mineral")

# Quick Start Guide

## 1. Get PySC2

### PyPI

The easiest way to get PySC2 is to use pip:

```shell
$ pip install git+https://github.com/deepmind/pysc2
```

Also, you have to install `baselines` library.

```shell
$ pip install git+https://github.com/openai/baselines
```

## 2. Install StarCraft II

### Mac / Win

You have to purchase StarCraft II and install it. Or even the Starter Edition will work.

http://us.battle.net/sc2/en/legacy-of-the-void/

### Linux Packages

Follow Blizzard's [documentation](https://github.com/Blizzard/s2client-proto#downloads) to
get the linux version. By default, PySC2 expects the game to live in
`~/StarCraftII/`.

* [3.16.1](http://blzdistsc2-a.akamaihd.net/Linux/SC2.3.16.1.zip)

## 3. Download Maps

Download the [ladder maps](https://github.com/Blizzard/s2client-proto#downloads)
and the [mini games](https://github.com/deepmind/pysc2/releases/download/v1.2/mini_games.zip)
and extract them to your `StarcraftII/Maps/` directory.

## 4. Train it!

```shell
$ python train_mineral_shards.py --algorithm=a2c
```

## 5. Enjoy it!

```shell
$ python enjoy_mineral_shards.py
```

## 4-1. Train it with DQN

```shell
$ python train_mineral_shards.py --algorithm=deepq --prioritized=True --dueling=True --timesteps=2000000 --exploration_fraction=0.2
```


## 4-2. Train it with A2C(A3C)

```shell
$ python train_mineral_shards.py --algorithm=a2c --num_agents=2 --num_scripts=2 --timesteps=2000000
```


|                      | Description                                     | Default                         | Parameter Type |
|----------------------|-------------------------------------------------|---------------------------------|----------------|
| map                  | Gym Environment                                 | CollectMineralShards            | string         |
| log                  | logging type  : tensorboard, stdout             | tensorboard                     | string         |
| algorithm            | Currently, support 2 algorithms  : deepq, a2c   | a2c                             | string         |
| timesteps            | Total training steps                            | 2000000                         | int            |
| exploration_fraction | exploration fraction                            | 0.5                             | float          |
| prioritized          | Whether using prioritized replay for DQN        | False                           | boolean        |
| dueling              | Whether using dueling network for DQN           | False                           | boolean        |
| lr                   | learning rate (if 0 set random e-5 ~ e-3)       | 0.0005                          | float          |
| num_agents           | number of agents for A2C                        | 4                               | int            |
| num_scripts          | number of scripted agents for A2C               | 4                               | int            |
| nsteps               | number of steps for update policy               | 20                              | int            |

#   n e x u s - w a r s - t r a i n i n g  
 #   n e x u s - w a r s - t r a i n i n g  
 