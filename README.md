# McGonagall
McGonagall is a prototyping system designed to prototype and test mobile apps. Unlike other systems, McGonagall maintains seperate prototype representations for the app designer (paper) and user (mixed-fidelity on iPhone). The wizard also uses the [Wizard Control Center](rppt.meteorapp.com) to see the user's iPhone interface and other metadata about the user (location, typed messages, etc). McGonagall is a research project in active development through [Design, Technology, and Research](http://dtr.northwestern.edu) at Northwestern University and advised by [Haoqi Zhang](http://users.eecs.northwestern.edu/~hq/).

## Approach
In McGonagall, a wizard maneuvers a purely paper prototype underneath a camera connected to the Wizard Control Center. This camera stream is sent to the user through the iOS app and any non-paper elements (digital or multi-fidelity, represented using [TopCodes](http://users.eecs.northwestern.edu/~mhorn/topcodes/)) are triggered at the appropriate location. The iOS app interface is then streamed back to the Wizard Control Center and overlaid with user gestures in real time.

### Interface Elements

#### Paper
Any drawings or paper elements (think paper prototyping) are streamed to the user's iPhone unchanged.

#### Digital
The wizard can move certain TopCodes into the camera feed to trigger interactive, digital elements on the iOS app. The system currently supports the native iOS keyboard, `UIImagePickerController`, `UIImageView` and `MKMapView`. The image view renders user-captured photos and both the image view and map view are displayed on top of their streamed paper representations on the iOS app (location is preserved between representations).

#### Multi-fidelity
Multi-fidelity elements are used to make physical modifications to any digital element (e.g. render a lo-fi, drawn Pokemon on a digital map). They consist of both a paper component and digital component. To trigger a multi-fidelity element, make physical modifications between the TopCode bounds of a native element in the paper representation (element must have a white background; white is our "green screen"). Then introduce the appropriate TopCode to the camera feed and the paper component will be extracted and rendered on top of the digital component. 

### TopCode Dictionary
Wizards can use following TopCodes to use the system out of the box. TopCodes are available at <http://users.eecs.northwestern.edu/~mhorn/topcodes/topcodes.pdf>.

#### Digital elements
  * Keyboard: 31
  * Camera: 361
  * Photo
    * Top left: 93
    * Top right: 155
    * Bottom left: 203
    * Bottom right: 271
  * Map
    * Top left: 157
    * Top right: 205
    * Bottom left: 279
    * Bottom right: 327
    
#### Multi-fidelity overlays
  * Camera Overlay: 331
  * Photo Overlay: 421
  * Map Overlay: 331

## Setup
See the READMEs in each submodule.

## Contact
Feel free to reach out with issues or questions!

Meg Grasse at [meggrasse@u.northwestern.edu](mailto:meggrasse@u.northwestern.edu)  
Andrew Finke
