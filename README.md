resize-jpg-in-caffeine
======================

Resize 4 sizes Photoshop CS3 AppleScript
//

#target photoshop

// in case we double clicked the file
bringToFront();
// Master function
// =======================================================
master ();
function master  ()
{       
 
 

/////////////// XL ///////////////
//create folder xl
var CurrentFolder = activeDocument.path;
var parentFolder = decodeURI(activeDocument.path.parent);
var xlFolder = new Folder(parentFolder + '/' + "xl");
if (xlFolder.exists == false) xlFolder.create();

//resize 200x200 for Sku.main
preferences.rulerUnits = Units.POINTS
app.activeDocument.resizeImage(500, 500, 72, ResampleMethod.BICUBICSMOOTHER);

//change the color mode RGB
var doc = app.activeDocument;
doc.changeMode(ChangeMode.RGB);
doc.BitsPerChannelType = BitsPerChannelType.EIGHT;

//save as different name for Sku.main image 
var doc = app.activeDocument;
var Path = doc.path;
var Name = doc.name.replace(/\.[^\.]+$/, ''); 
var Suffix = ".xl";
var saveFile = new File(xlFolder + "/" + Name + Suffix + ".jpg");
SaveJPEG(saveFile, 10);

//save option
function SaveJPEG(saveFile, jpegQuality){
jpgSaveOptions = new JPEGSaveOptions();
jpgSaveOptions.embedColorProfile = true;
jpgSaveOptions.formatOptions = FormatOptions.STANDARDBASELINE;
jpgSaveOptions.matte = MatteType.NONE;
jpgSaveOptions.quality = 10;
app.activeDocument.saveAs(saveFile, jpgSaveOptions, true, Extension.LOWERCASE);
}

/////////////// MAIN ///////////////

//create folder 
var CurrentFolder = activeDocument.path;
var parentFolder = decodeURI(activeDocument.path.parent);
var mainFolder = new Folder(parentFolder + '/' + "main");
if (mainFolder.exists == false) mainFolder.create();

//resize 200x200 for Sku.main
preferences.rulerUnits = Units.POINTS
app.activeDocument.resizeImage(200, 200, undefined, ResampleMethod.BICUBICSMOOTHER);


//save name for Sku.main
var doc = app.activeDocument;
var Path = doc.path;
var Name = doc.name.replace(/\.[^\.]+$/, ''); 
var Suffix = ".main";
var saveFile = File(mainFolder + "/" + Name + Suffix + ".jpg");
SaveJPEG(saveFile, 10);

//save option
function SaveJPEG(saveFile, jpegQuality){
jpgSaveOptions = new JPEGSaveOptions();
jpgSaveOptions.embedColorProfile = true;
jpgSaveOptions.formatOptions = FormatOptions.STANDARDBASELINE;
jpgSaveOptions.matte = MatteType.NONE;
jpgSaveOptions.quality = 10;
app.activeDocument.saveAs(saveFile, jpgSaveOptions, true, Extension.LOWERCASE);
}

/////////////// MED ///////////////

//create folder 
var CurrentFolder = activeDocument.path;
var parentFolder = decodeURI(activeDocument.path.parent);
var medFolder = new Folder(parentFolder + '/' + "med");
if (medFolder.exists == false) medFolder.create();

//resize 100x100 for Sku.med
preferences.rulerUnits = Units.POINTS
app.activeDocument.resizeImage(100, 100, undefined, ResampleMethod.BICUBICSMOOTHER);

//save name for Sku.med
var doc = app.activeDocument;
var Path = doc.path;
var Name = doc.name.replace(/\.[^\.]+$/, ''); 
var Suffix = ".med";
var saveFile = File(medFolder + "/" + Name + Suffix + ".jpg");
SaveJPEG(saveFile, 10);

//save option
function SaveJPEG(saveFile, jpegQuality){
jpgSaveOptions = new JPEGSaveOptions();
jpgSaveOptions.embedColorProfile = true;
jpgSaveOptions.formatOptions = FormatOptions.STANDARDBASELINE;
jpgSaveOptions.matte = MatteType.NONE;
jpgSaveOptions.quality = 10;
app.activeDocument.saveAs(saveFile, jpgSaveOptions, true, Extension.LOWERCASE);
}

/////////////// SMALL ///////////////

//create folder 
var CurrentFolder = activeDocument.path;
var parentFolder = decodeURI(activeDocument.path.parent);
var smallFolder = new Folder(parentFolder + '/' + "small");
if (smallFolder.exists == false) smallFolder.create();

//resize 50x50 for Sku.small
preferences.rulerUnits = Units.POINTS
app.activeDocument.resizeImage(50, 50, undefined, ResampleMethod.BICUBICSMOOTHER);

//save name for Sku.small
var doc = app.activeDocument;
var Path = doc.path;
var Name = doc.name.replace(/\.[^\.]+$/, ''); 
var Suffix = ".small";
var saveFile = File(smallFolder + "/" + Name + Suffix + ".jpg");
SaveJPEG(saveFile, 10);

//save option
function SaveJPEG(saveFile, jpegQuality){
jpgSaveOptions = new JPEGSaveOptions();
jpgSaveOptions.embedColorProfile = true;
jpgSaveOptions.formatOptions = FormatOptions.STANDARDBASELINE;
jpgSaveOptions.matte = MatteType.NONE;
jpgSaveOptions.quality = 10;
app.activeDocument.saveAs(saveFile, jpgSaveOptions, true, Extension.LOWERCASE);
}

//////////////////////////////////////
//close file
doc.close(SaveOptions.DONOTSAVECHANGES);
beep();
master ();

      
}
////////////////////////////////////
//end function


        

