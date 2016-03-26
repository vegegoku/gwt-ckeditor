# Quick start with gwt-ckeditor #

## Install ##

Download the JAR distribution available in Download section.

Add the JAR to your classpath

Edit your App.gwt.xml file :

### Inherits Gwtckeditor ###
```
<inherits name='com.axeiya.gwtckeditor.Gwtckeditor'/>
```

### Keep in mind your "rename-to" directive ###
For example :
```
<module rename-to='cksample'>
```
Its content is useful for JS files importation (here "cksample")

### Edit your App.html file ###
Add JS importation :
```
<script type="text/javascript">
   var CKEDITOR_BASEPATH = 'cksample/ckeditor/';
</script>
```

The variable CKEDITOR\_BASEPATH is used to define your ckeditor path. Replace "cksample" by your project name, as it appears in the "rename-to" directive.

## Use ##
### Basic example ###
```
CKEditor ckee = new CKEditor();
RootPanel.get().add(ckee);
```

### Full example ###
```
CKEditor ckee = new CKEditor(CKConfig.full);
RootPanel.get().add(ckee);
```

### Custom example ###
```
		//Creates a new config, with FULL preset toolbar as default
		CKConfig ckf = new CKConfig(PRESET_TOOLBAR.FULL);
		//Setting background color
		ckf.setUiColor("#000000");
		//Setting size
		ckf.setWidth("1000px");
		ckf.setHeight("500px");
		
		//Creating personalized toolbar
		ToolbarLine line = new ToolbarLine();
		//Define the first line
		TOOLBAR_OPTIONS[] t1 = {TOOLBAR_OPTIONS.Source,TOOLBAR_OPTIONS._,TOOLBAR_OPTIONS.Save,TOOLBAR_OPTIONS.NewPage,TOOLBAR_OPTIONS.Preview,TOOLBAR_OPTIONS._,TOOLBAR_OPTIONS.Templates};
		line.addAll(t1);
		
		//Define the second line
		ToolbarLine line2 = new ToolbarLine();
		line2.add(TOOLBAR_OPTIONS.Cut);
		line2.add(TOOLBAR_OPTIONS.Copy);
		line2.add(TOOLBAR_OPTIONS.Paste);
		line2.addBlockSeparator();
		line2.add(TOOLBAR_OPTIONS.PasteFromWord);
		
		//Creates the toolbar
		Toolbar t = new Toolbar();
		t.add(line);
		t.addSeparator();
		t.add(line2);
		
		//Set the toolbar to the config (replace the FULL preset toolbar)
		ckf.setToolbar(t);

		//Creates the editor with this config
		final CKEditor cke = new CKEditor(true,ckf);
		RootPanel.get().add(cke);
		
		//plays with get/setText
		Button b = new Button("contenu");
		b.addClickHandler(new ClickHandler() {
			@Override
			public void onClick(ClickEvent event) {
				Window.alert(cke.getText());
				cke.setText("un texte");
			}
		});
		RootPanel.get().add(b);
```

You can launch your application.