# Machine Vision Algorithms and Applications

Notes (and summary) on/of the book 'Machine Vision Algorithms and Applications', by Carsten Steger, Markus Ulrich and Christian Wiedemann.

# Chapter 1: Introduction

## 1.1 Common tasks solved in machine vision

* Object identification: classify
* Position detection: locate known objects
* Completeness checking
	- Was product assembled correctly?
* Shape and dimensional inspection: check geometric parameters
* Surface inspection: scratches, etc.

## 1.2 Components of a typical machine vision system

*See Fig 1.1, page 2.*

* Object carried maybe in conveyor belt
* Photoelectric sensor triggers camera, which acquires image
	- Lens an dobjective of the camera carefully chosen
* Object illuminated with specially designed illumination
	- Example: stroboscopic lamp = flashes, instants illuminated
* Camera deliver image to a camera-computer interface
	- example: a frame grabber
	- if not a frame grabber, we can use a standard interface
		- Firewire
		- USB (3)
		- Ethernet
* Computer can be: regular, industrial PC, computer integrated to camera (embedded devices)
* Computer can have
	- a standard processor
	- a digital signal processor (DSP)
	- a fiel-programmable gate array (FPGA)
* Image processing happens and an action can be triggered
	- Action is communicated to a controller, eg a PLC
	- The controller communicates and activates an actuator
		- Interfaces
			- Time critical, realtime: fieldbus
			- Non time-critical: ethernet

# Chapter 2: Image Acquisition

## 2.1 Illumination

### 2.1.1 Electromagnetic Radiation

* Light: electromagnetic radiation
* Black body: absorbs all electromagnetic radiation and serves as an ideal source of thermal radiation
	- Therefore, radiance is function of temperature...
* Spectral radiance of a black body given by Planck's law
	- I(lambda, T) = spectral radiance = k1 / (lambda^5 * (exp(k2/(lambda*T)) - 1))
		- *See formula and image: Fig. 2.1, page 7*
		- lambda: wave length - visible: 380-780 nm
		- T: temperature
			- 1000K: red glow
			- 3000K: lamp
			- 6500K: daylight

### 2.1.2 Types of light sources

* Incandescent lamps: filament which works as a resistance in vacuum
	- 5% efficiency
	- Color temperature: 3000 - 4000K
* Xenon lamps: sealed lamp with xenon, which is ionized
	- Temperature: 5500 - 12000K
	- 200 flashes/second
* Fluorescent lamps
	- Mercury vapor exited in noble gas (eg, argon), causing UV radiation
	- Temperature: 3000 - 6000K
	- Alternate current: flickering lamp -- for machine vision, this must be avoided using alternate currents of about 22 kHz
* LEDs: Light Emitting Diodes: used primarily in machine vision applications
	- Direct current
	- Diodes that emit light
	- Large longevity: 100k hours
	- Can be used as flashes, with fast response time
	- Little power consumed and little heat produced

### 2.1.3 Interaction of Light and Matter

* Microstructure of the matter/object/surface determined reflection of light
* Light incident onto a surface can be
	- Reflected
		- Diffuse: light reflected and scattered in all directions
		- Specular: light reflected in one direction: incoming and reflected light in a single plane and their angles wrt surface normal (macrostructure) are constant -- example: mirror
	-  Transmitted (eg, with semi/transparent surfaces)
		- Diffuse: goes through materia in a scattered manner
		- Direct: goes through material in a given direction; refraction occurs usually: incidence direction is changed inside material
	- Absorbed: radiation energy absorbed by surface material: converted into heat
* Fraction of light reflected by a surface determined by the Bidirectional Reflectance Distribution Function (BRDF)

### 2.1.4 Using the Spectral Composition of the Illumination

* Example in practice: if a red object in green background needs to be enhanced, red illumination can be used: red object will appear bright and green dark
* CCD and CMOS sensors are sensitive to IR light: same effect: they are enhanced
* Polarization
	- Light becomes partially polarized through reflection in metallic surfaces: it takes certain directions -- ie, angle of EM waves wrt ray of incidence
	- Polarizing filters suppress polarized light: reflections in a given direction
	- Even better suppression if the light source is polarized
		- Light source is polarized with filter
		- A filter called analyzed is used in front of the camera which filters all polarized rays → specular reflections are suppressed

### 2.1.5 Using the Directional Properties of the Illumination

* Light ray direction can be
	- Diffuse: all directions
	- Narrow range of directions, parallel rays: directed/telecentric illumination
* Light source placement can be
	- Front: same side of camera (pointing in the same direction as cameras)
	- Back: the opposite side of the object to the camera
* Angle of reflected light can be
	- Bright-field: angle light source so that light reflect to camera
	- Dark-field: angle light source so that light reflected away from camera
* The above features can be combined and used in suited scenarios
	- Diffuse + front + bright-field: homogeneous lighting, avoid shadows, look through transparent objects
	- Directed/Telecentric + front + bright-field: create shadows around objects of interest; parts parallel to image plane reflect light to camera
	- Directed/Telecentric + front + dark-field: highlight indentations and protussions on rather planar surfaces, eg coin engravings, braille dots, scratches
	- Diffuse + back + bright-field: almost planar objects (small depth) acquired with white background and whole object dark/black: silhouette of opaque objects
	- Directed/telecentric + back + bright-field: as before, silhouette of object captured; telecentric lenses are necessary for the camera and the light source must be aligned with camera; very sharp edges and no perspective distorsions --> often used for measuring

## 2.2 Lenses

## 2.3 Cameras

## 2.4 Camera-Computer Interfaces

## 2.5 3D Image Acquisition Devices

