# 🎛 User Interface

**VariText** is a Cinema 4D Object plug-in. You can find it in application menu **Plugins ( Extentions) > VariText**.

<figure><img src="../.gitbook/assets/Screenshot 2023 07 04 at 11.05.23.png" alt=""><figcaption></figcaption></figure>

VariText v1.0 supports only variable fonts. You can use fonts already preinstalled with the plugin.

{% hint style="warning" %}
Some fonts are poorly designed and will have noticeable overlapping edges. VariText for Cinema 4D cannot improve these faults. Always use high quality fonts for best results.
{% endhint %}

Go to tab **Info >** **About** button to find more information about plug-in registration and tutorials.

### Usage

**VariText** creates in a Cinema 4D scene a new _Spline Generator_ object. To know how to use splines please take a look this [article](https://help.maxon.net/c4d/s26/en-us/Default.htm#html/5420.html?TocPath=Create%2520Menu%257CSpline%257C\_\_\_\_\_0).

### Options

#### Object tab

**Text.** Enter the text into the Text box. You can enter up to multiple lines of text — press Return to start a new line. The text appears in the viewport as a spline primitive when click outside the text box.

**Font.** Only OpenType and True Type variable fonts supported.

**Font Style.** Each font have at least one style (italic, bold, black, regular) here you can choose one.

**Font Axes.** A variable font axis refers to a specific attribute or characteristic that can be adjusted within a variable font. Variable fonts are a new font format that allows for dynamic variation in a range of attributes, such as weight, width, slant, and more. Each of these attributes corresponds to a specific axis.

**Align.** Set the text’s alignment to left-aligned, centered or right-aligned.

**Height.** The height of the letters.

**Horizontal Spacing.** With these command you can insert space between the characters.

**Vertical Spacing.** With these command you can insert space between the text lines.

**Word Spacing.** With these command you can adjust space between words.

**Plane.** These options define the direction in which the object will "point". Using these options it is easier - and faster - to rotate the object (without rotating the object coordinate system as well).

**Reverse.** Enabling this option will reverse the point order of the spline. See more [here](https://help.maxon.net/c4d/s26/en-us/Content/html/5420.html).

**Intermediate Points.** Here you can define how the spline is further subdivided with intermediate points. See more [here](https://help.maxon.net/c4d/s26/en-us/Default.htm#html/OSPLINETEXT-ID\_OBJECTPROPERTIES.html#SPLINEOBJECT\_INTERPOLATION).

**Number**, **Angle** and **Maximum Length** works like [for standart Cinema 4D splines](https://help.maxon.net/c4d/s26/en-us/Default.htm#html/OSPLINETEXT-ID\_OBJECTPROPERTIES.html#SPLINEOBJECT\_ANGLE).

#### Falloff tab

With this options you can animate variation axes with Cinema 4D Fields functionality.

**Font axes.** Select exis which you want to animate with Fields.

**Enabled.** Enable fields for selected font axis.

**Apply To.** Select text part which be affected by fields separetely.

**Pivot.** Ajust position of fields sampling center. Usually it is a center of character, word or line of text.

**Fields.** Fields user interface. You unfamiliar with **Fields Cinema 4D functionality** please [go here](https://help.maxon.net/c4d/s26/en-us/Default.htm#html/OEPLAIN-FALLOFF\_GROUPFALLOFF.html#FIELDS).

#### Options tab

**Display.** These settings serve as visual aides for the depiction of various properties.

**Bake to spline.** Create PLA animated spline object from VariText generator. After clicking Bake button a new spline object will be created.&#x20;

_Start and End: Animation time range to bake._

_Mode_. Define here what should happen at the end of the animation:

* _Play_: The animation stops.
* _Loop_: The animation will begin again.
* _Ping-Pong_: The animation will run continually forwards and backwards.

_Loop. Define loops count for animation modes Loop and Ping-Pong._

#### Info tab

**Fonts Licensing Info.** Here finds info about fonts included into VariText installation.

**Log.** With this section user can trace VariText errors and send it to support team.

**About** button open an additional dialog window with _Manage License_ button, this online help and feedback page.
