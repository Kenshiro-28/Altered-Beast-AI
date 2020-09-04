# Altered Beast AI

This is an Altered Beast artificial intelligence based on the T-Rex evolutionary neural network. It trains playing the game until it's unable to improve its best score. After completing the training, the program plays a last game rendering the game screen.

## Game information

Altered Beast is a 1988 beat 'em up arcade game developed and manufactured by Sega. The game is set in Ancient Greece and follows a player character resurrected by Zeus to rescue his daughter Athena from the ruler of the underworld, Neff. Through the use of power-ups, the player character can assume the form of different magical beasts. After its initial arcade release, it was ported to several home video game consoles and home computers, including the Sega Genesis, for which it was a pack-in game.

The game was developed by Makoto Uchida, who developed the game as his first project as a lead developer. Uchida and his team used the System 16 arcade system board for its graphical capabilities with sprites. Altered Beast was ported numerous times in addition to its Genesis conversion, including for the Master System by Sega and to several computer systems and video game consoles by various third parties.

This program uses the Sega Genesis console emulator provided by OpenAI Gym Retro.

## Neural network information

T-Rex is an evolutionary neural network. It learns by adjusting the strength of the connection weights by mutation and selection. The programmer must define the problem to solve with a scoring system so that T-Rex can evolve gradually until finding the optimal solution.

Main features:

- Binary feedforward neural network
- Configurable number of inputs, hidden layers and outputs
- Developed using object-oriented programming
- Fast, robust and portable

### Input layer

The input of the neural network is the screen output of the Sega Genesis console. The original image is processed with Canny edge detection to extract useful structural information and dramatically reduce the amount of data to be processed. Finally, the image resolution is reduced to one third of its original size. The input layer has 23893 neurons.

### Hidden layer

The neural network has 1 hidden layer. The T-Rex architecture states that the number of neurons in each hidden layer is set as the number of input neurons, so it has 23893 neurons.

### Output layer

The neural network outputs are the button activations on the player's gamepad. As the game emulation provides 12 buttons, the output layer has 12 neurons.

## Installing dependencies

### T-Rex

You must compile T-Rex as a shared library:

https://github.com/Kenshiro-28/T-Rex

Copy the generated file **libT-Rex.so** in the folder /usr/local/lib

Run this command to add the folder to the library path:

```
$ sudo ldconfig /usr/local/lib
```

Copy the header files in the folder /usr/local/include/T-Rex

``` 
T-Rex
   ├── data_tier
   │   └── DataManager.h
   ├── logic_tier
   │   ├── NeuralLayer.h
   │   └── NeuralNetwork.h
   └── presentation_tier
       └── ConsoleManager.h
```

### Python

Run this command to install Python:

```
$ sudo apt install python3-dev python3-pip python3-wheel python3-opencv
```

### OpenAI Gym Retro

Run this command to install OpenAI Gym Retro:

```
$ pip3 install gym-retro
```

### Game ROM

This program has been tested with the USA-Europe version of the game. Run this command in the folder containing the ROM file:

```
$ python3 -m retro.import ./
```

## Running

Run this command in the root folder to start the program:

```
$ python3 altered-beast.py
```

This project includes a trained neural network. Running the program will skip the training phase if there is a neural network file in the same folder. To train a new neural network, delete the file **neural_network.json**.

----- Work in progress -----
