Day 11: Simple Temperature Classifier
This project uses an ESP32 to classify temperature readings as Low, Medium, or High with a small dense neural network. The ESP32 prints each test reading, its predicted class, and the model’s confidence scores to the Serial Monitor.

Components
- ESP32 DevKit board
Classification Labels
- Low: below 20°C
- Medium: 20°C to 30°C
- High: above 30°C

Wokwi Simulation
Create an ESP32 project in Wokwi and add these files from the repository:
- sketch.ino
- diagram.json

How to use
1. Start the Wokwi simulation.
2. Open the Serial Monitor at 115200 baud.
3. View the sample temperature readings, predicted classes, and confidence scores.
4. Edit the testTemps array in sketch.ino to try different readings.

Run the simulation(https://wokwi.com/projects/476865789498987521).

How it works
The sketch normalizes each temperature using:
x = (temperature - 25) / 15
The normalized value passes through a dense hidden layer with four neurons and ReLU activation. A three-neuron output layer produces scores for the Low, Medium, and High classes. Softmax converts these scores into confidence values.
The model weights are included directly in the sketch, so it performs inference only. It does not train on a labeled dataset.

Files
- sketch.ino — ESP32 code for temperature classification
- diagram.json — Wokwi ESP32 board and Serial Monitor configuration

Note
The displayed confidence values are the model’s softmax outputs. They are not a guarantee of real-world accuracy.
