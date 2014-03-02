Simple ImageView subclass that allows for overlayed text/label. 

Custom properites include:

* Text  - The text for the label. 
* Text Size - The size of the font in pixels. (note do not add sp or px, just put the int) 
* Text Color - The color of the text. 
* Text Style  - The style of the tex. (Bold, Italic, BoldItalic) 
* Custom Font - The string of the custom font file in assets folder. ("myfont.ttf") 
* Label Postion - The position of the text. (Top Left, Top Right, Top Center, Bottom Left, Bottom Right, Bottom Center, Center) 
* X Offset - X offset for any of the positions above, to further customize location on screen. 
* Y Offset - Y offset for any of the positions above, to further customize location on screen. 

![alt tag](https://raw.github.com/DejanRistic/LabeledImageView/master/assets/Screenshot_2014-03-02-17-48-35.png)


Integration Instructions:

First make sure you setup the custom attributes, to do so copy this into your attrs.xml under the resources tag.

    <declare-styleable name="LabeledImageView">
        <attr name="xOffset" format="float" />
        <attr name="yOffset" format="float" />
        <attr name="text" format="string" />
        <attr name="textSizePx" format="float" />
        <attr name="textColor" format="color" />
        <attr name="customFont" format="string"/>
        <attr name="textStyle" format="enum">
            <enum name="normal" value="0" />
            <enum name="bold" value="1" />
            <enum name="italic" value="2" />
            <enum name="boldItalic" value="3" />
        </attr>
        <attr name="labelPosition" format="enum">
            <enum name="topLeft" value="0" />
            <enum name="topRight" value="1" />
            <enum name="bottomLeft" value="2" />
            <enum name="bottomRight" value="3" />
            <enum name="topCenter" value="4" />
            <enum name="bottomCenter" value="5" />
            <enum name="center" value="6" />
        </attr>
    </declare-styleable>
    
    
Then in any layout where you will use the widget make sure to add this line to your root element:

    xmlns:custom="http://schemas.android.com/apk/res-auto"
    
In Eclipse, if the previous line gives you trouble you can try the following:

    xmlns:app="http://schemas.android.com/apk/res/com.yourpackage.LabeledImageView"
    
Then you are ready to use the LabeledImageView in your layout, here is an example (if using the second line form above replace custom with app):

      <com.fuzzydev.LabeledImageView
        android:id="@+id/my_image"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:contentDescription="@string/description"
        android:scaleType="fitXY"
        android:src="@drawable/my_picture"
        custom:labelPosition="bottomLeft"
        custom:text="My Image Label"
        custom:textColor="@android:color/black"
        custom:textStyle="bold" />
    

You can also add the ImageView and set all the custom attributes programmatically just like any normal ImageView.
