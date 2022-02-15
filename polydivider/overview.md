# Overview

**PolyDivider** is a **Cinema 4D** deformer plugin that makes procedural subdividions on polygon meshes or primitives allowing the user to create rectangular style topology.

### Usage

**PolyDivider** creates in a Cinema 4D scene a new _deformer_ object. To know how to use deformers please take a look [this article](https://help.maxon.net/us/index.html#5460).&#x20;

### Options

![PolyDivider interface](../.gitbook/assets/annotation-2020-05-21-122350.jpg)

#### Iterations <a href="#dividerobject_sub" id="dividerobject_sub"></a>

Each polygon of a deformable object is recursively divided into two new polygons according to the number of iterations.

![](../.gitbook/assets/mikeudin\_polydivider\_help-iterations.jpg)

#### Manual <a href="#dividerobject_manuald" id="dividerobject_manuald"></a>

This setting can be opened by clicking on the small triangle to the left of the **Iteration** option. Here you can specify the number of polygons iterations separately for vertical and horizontal splitting

#### Seed <a href="#dividerobject_seed" id="dividerobject_seed"></a>

Changing the **Seed** value will result in entirely different random iterations result.

#### Variation <a href="#dividerobject_plusmin" id="dividerobject_plusmin"></a>

Varies the size proportions of the newly created polygons.&#x20;

* **0%** - Polygons size the same.&#x20;
* **100%** - Polygons size different.

![](../.gitbook/assets/variation.jpg)

#### X Offset, Y Offset <a href="#dividerobject_plusx" id="dividerobject_plusx"></a>

Change polygons size by moving on perpendicular directions of the source polygon plane

#### Alternative Offset <a href="#dividerobject_reverseplus" id="dividerobject_reverseplus"></a>

Makes offset function more variable

#### Scale <a href="#dividerobject_scale" id="dividerobject_scale"></a>

Polygons scaling

#### Slide <a href="#dividerobject_slidepower" id="dividerobject_slidepower"></a>

![](../.gitbook/assets/slide-with-linear-field.jpg)

With the **Slide** option, polygon edges can be moved  along their surface. It works like **Scale** option but from particilar edge. Polygon sliding can be managed using Fields with it direction and strength.&#x20;

#### Angle <a href="#dividerobject_slide" id="dividerobject_slide"></a>

Polygon sliding can be done with rotation movement. This option indicates start angle when polygon starts sliding. **Spline** feature helps to adjust animation for more convinient result.&#x20;

#### Extrude <a href="#dividerobject_extrude" id="dividerobject_extrude"></a>

This option extrudes polygons like a [Cinema 4D Extrude Tool ](https://help.maxon.net/us/index.html#TOOLEXTRUDE)

![](../.gitbook/assets/extrude-and-scale.jpg)

#### Caps <a href="#dividerobject_extrudecaps" id="dividerobject_extrudecaps"></a>

Enable this option to create a cap at the base of the extrusion. This gives you a quick way to create a closed volume.

#### Extrude Inner <a href="#dividerobject_extrudeinner" id="dividerobject_extrudeinner"></a>

This option operates in a similar way to _Extrude_ but the polygons are extruded inwards.

#### Mode <a href="#dividerobject_exmode" id="dividerobject_exmode"></a>

_Extrude Inner_ option modes:&#x20;

* **Default** - Standart mode&#x20;
* **Hole** - Only extruded polygons&#x20;
* **Invert** - Without extruded polygons

![](../.gitbook/assets/extrude-inner.jpg)

#### Field Precision <a href="#dividerobject_fieldpresc" id="dividerobject_fieldpresc"></a>

This option setting up polygon sensibility to fields&#x20;

#### Optimize Tolerance <a href="#dividerobject_tolerance" id="dividerobject_tolerance"></a>

After each iteration plugin optimizes geometry. To eliminating points you may enter a tolerance value. If points are closer to each other than this value, then they are merged into one point; if the points are further apart than the value, they will not be merged. If polygons become redundant (e.g., if all three corner points of the polygon occupy the same point), CINEMA 4D will automatically delete them.

#### Fields

![](../.gitbook/assets/fields.jpg)

_Iterations, Scale, Extrude, Extrude Inner_ and Slide parameters can be changed using the [**Cinema 4D Fields System**](https://www.youtube.com/watch?v=Vzt4midvx30). Create a Field object, drag it to the Linkbox of the parameter you need, or click the **Create** button to add a new Group Field. Read more about how **Cinema 4D Fields System** works [here](https://help.maxon.net/us/index.html#58091). See examples in the **Videotutorials** section.

#### About

![](../.gitbook/assets/about.jpg)

In this dialog box, you can activate/deactivate the plugin, open **Online Help** page or the plugin's official page and send feedback message by email.

