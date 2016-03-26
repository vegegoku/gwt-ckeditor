You can test this sample here : http://apps.axeiya.com/TestCK/
```
public void onModuleLoad() {
		final CKEditor cke = new CKEditor(CKConfig.full);
		RootPanel.get("full").add(cke);

		final CKEditor ckeb = new CKEditor(CKConfig.basic);
		RootPanel.get("basic").add(ckeb);

		CKConfig CONFIG_MODIFICATION = new CKConfig();
		// Creating personalized toolbar
		ToolbarLine line = new ToolbarLine();
		// Define the first line
		TOOLBAR_OPTIONS[] t1 = { TOOLBAR_OPTIONS.Save, TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.Cut, TOOLBAR_OPTIONS.Copy,TOOLBAR_OPTIONS.Paste, TOOLBAR_OPTIONS.PasteText,TOOLBAR_OPTIONS.PasteFromWord, TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.SpellChecker, TOOLBAR_OPTIONS.Scayt,TOOLBAR_OPTIONS._, 
				TOOLBAR_OPTIONS.Undo, TOOLBAR_OPTIONS.Redo,TOOLBAR_OPTIONS._, 
				TOOLBAR_OPTIONS.Find,TOOLBAR_OPTIONS.Replace, TOOLBAR_OPTIONS._ };
		line.addAll(t1);

		// Define the second line
		ToolbarLine line2 = new ToolbarLine();
		TOOLBAR_OPTIONS[] t2 = { 
				TOOLBAR_OPTIONS.Bold, TOOLBAR_OPTIONS.Italic,TOOLBAR_OPTIONS.Underline, TOOLBAR_OPTIONS.Strike,
				TOOLBAR_OPTIONS.Subscript, TOOLBAR_OPTIONS.Superscript, TOOLBAR_OPTIONS._, 
				TOOLBAR_OPTIONS.NumberedList,TOOLBAR_OPTIONS.BulletedList, TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.Outdent, TOOLBAR_OPTIONS.Indent,TOOLBAR_OPTIONS.Blockquote, TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.JustifyLeft, TOOLBAR_OPTIONS.JustifyCenter,	TOOLBAR_OPTIONS.JustifyRight, TOOLBAR_OPTIONS.JustifyBlock,	TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.Image,TOOLBAR_OPTIONS.Table, TOOLBAR_OPTIONS.HorizontalRule,TOOLBAR_OPTIONS.SpecialChar };
		line2.addAll(t2);

		//define the third line
		ToolbarLine line3 = new ToolbarLine();
		TOOLBAR_OPTIONS[] t3 = { 
				TOOLBAR_OPTIONS.Styles,	TOOLBAR_OPTIONS.Format, TOOLBAR_OPTIONS.Font, TOOLBAR_OPTIONS.FontSize, TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.TextColor, TOOLBAR_OPTIONS.BGColor,	TOOLBAR_OPTIONS._,
				TOOLBAR_OPTIONS.ShowBlocks };
		line3.addAll(t3);

		// Creates the toolbar
		Toolbar t = new Toolbar();
		t.add(line);
		t.addSeparator();
		t.add(line2);
		t.addSeparator();
		t.add(line3);

		// sets some params
		CONFIG_MODIFICATION.setResizeMinWidth(520);
		CONFIG_MODIFICATION.setResizeMinHeight(250);
		CONFIG_MODIFICATION.setResizeMaxWidth(1600);
		CONFIG_MODIFICATION.setResizeMaxHeight(1600);
		CONFIG_MODIFICATION.setEntities_latin(false);
		CONFIG_MODIFICATION.setEntities(false);
		CONFIG_MODIFICATION.setWidth(Window.getClientWidth() / 2 + "");
		// Set the toolbar to the config (replace the FULL preset toolbar)
		CONFIG_MODIFICATION.setToolbar(t);
		
		final CKEditor ckec = new CKEditor(CONFIG_MODIFICATION);
		RootPanel.get("config").add(ckec);

	}
```