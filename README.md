
# Server-NodeJsSerialPortserver-socket.ioReact
## microbit-serial-port-nodejs

## Available Scripts

In the project directory, you can run:

### `npm run start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

## Microbit board javascript code

serial.onDataReceived(serial.readString(), function () {
    serial.writeLine("received")
})
input.onButtonPressed(Button.A, function () {
    // serial.writeLine("a")
    serial.writeLine("a")
})
input.onButtonPressed(Button.AB, function () {
    serial.writeLine("d")
})
input.onButtonPressed(Button.B, function () {
    serial.writeLine("b")
})
input.onGesture(Gesture.Shake, function () {
    serial.writeLine("s")
})
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    serial.writeLine("l")
})
// input.calibrateCompass()
serial.redirectToUSB()
basic.forever(function () {
    // serial.writeLine("a")
    serial.writeLine("p" + input.rotation(Rotation.Pitch))
    basic.pause(200)
    serial.writeLine("w" + input.compassHeading())
    basic.pause(200)
    serial.writeLine("r" + input.rotation(Rotation.Roll))
    basic.pause(200)
    serial.writeLine("t" + input.temperature())
    basic.pause(200)
    serial.writeLine("g" + input.lightLevel())
    basic.pause(200)
    serial.writeLine("x" + input.acceleration(Dimension.X))
    basic.pause(200)
    serial.writeLine("y" + input.acceleration(Dimension.Y))
    basic.pause(200)
    serial.writeLine("z" + input.acceleration(Dimension.Z))
    basic.pause(200)
    serial.writeLine("u" + input.soundLevel())
    basic.pause(200)
})

