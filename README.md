# robot-factory
Robot factory implementatin using prototypes.

BaseRobot
- BaseRobot function constructor takes name, weight, coords, chipVersion and sets them for his instances;
- BaseRobot prototype has methods goForward, goBack, goRight, goLeft, which can take step prop or move the robot by 1 in the appropriate direction in the case when step is undefined;
- BaseRobot prototype has method getInfo, which returns a string in the format Robot: %name%, Chip version: %chipVersion%, Weight: %weight%;

FlyingRobot
- FlyingRobot prototype inherits BaseRobot prototype;
- FlyingRobot constructor takes name, weight, coords, chipVersion, and transmits them to BaseRobot constructor;
- FlyingRobot constructor sets z coordinate to coords object of his instances;
- FlyingRobot prototype has methods goUp and goDown, which can take step prop or move the robot by 1 in the z coordinate in the case when step is undefined;
- The instance of FlyingRobot can use all methods from BaseRobot and FlyingRobot prototypes;

DeliveryDrone
- DeliveryDrone prototype inherits FlyingRobot prototype;
- DeliveryDrone constructor takes name, weight, coords, chipVersion, and transmits them to FlyingRobot constructor;
- DeliveryDrone constructor takes maxLoadWeight, currentLoad and sets it to his instances;
- DeliveryDrone prototype has method hookLoad, which saved the load object to currentLoad of DeliveryDrone instances if weight of cargo less than maxLoadWeight of drone;
- DeliveryDrone prototype has method unhookLoad, which sets initial value null to currentLoad;
- If the DeliveryDrone instance is loaded with another load, hookLoad method should not replace the previous load with a new load.
- The instance of DeliveryDrone can use all methods of BaseRobot, FlyingRobot, DeliveryDrone prototypes;
