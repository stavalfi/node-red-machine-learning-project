# Node red project - TV Channels

##### Presentors:
* [Matan]()
* [Tomer]()
* [Stav Alfi](https://github.com/stavalfi)
* [Elior Sastiel](https://github.com/eliorsastiel1)
* [Amir]()

##### Technologies:

* ESP 32
* MQTT Protocol
* Machine learning
* Mongodb
* JavaScript ES6
* GUI using Node-Red
* Android application

##### Machine learning:

__Library:__ [node-red-contrib-machine-learning](https://flows.nodered.org/node/node-red-contrib-machine-learning)

__Notes:__ 
1. Currently, there is a reported and unresolved bug in their repository.
The bug - Node red can't find any of the files you provided the path to them in the nodes.
__Solution (Works in Linux distributions and MacOS):__ Provide the full path to your files (as we did in this project). ___We couldn't make it work in Windows.___

2. The `decision tree classifier predictor` node accepts arrays in an array of data and returns the prediction. Have a look at how we sent him data from `message to array for prediction` node. Each sub-array corresponds to data that should be sent to get a prediction:

```javascript 1.6
return {
    payload: [[...msg.payload.user_code,msg.payload.datetime]]
};
