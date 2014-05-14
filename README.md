# zdk-tab

zdk-tabs and zdk-tab are two basic web components based on the polymer project.
 
To use these components just type :

    bower install zdk-tabs -S
    
Then in the header of your html file add the following lines to import the components :

    <script src="/bower_components/platform/platform.js"></script>
	<link rel="import" href="/bower_components/zdk-tabs/zdk-tabs.htm">
    
Then in the body of the html file :

    <zdk-tabs>
		<zdk-tab heading="tab 1">
            <p>Tab 1</p>
            <p>First tab is active by default</p>
		</zdk-tab>
		<zdk-tab heading="tab 2">
            <p>Tab 2 content</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat</p>
		</zdk-tab>
	</zdk-tabs>
    
You can add tabs on the fly programming, component updates itself.

    function addTab() {
		var newTab = document.createElement("zdk-tab");
		var tabNum = document.querySelectorAll("zdk-tab").length + 1
		newTab.setAttribute("heading","tab "+tabNum);
		var content = "<p>Tab "+tabNum+"</p>";
		for(var n=0;n<tabNum;n++) {
			content += "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat</p>";
		}
		newTab.innerHTML = content;
		document.querySelector("zdk-tabs").appendChild(newTab);
	}
    
The "zdk-tabs" component publishes the "selected" attribute in read/write. This attribute allows to read the index of the selected tab (read) or select a given tab (write).

    var tabs = document.querySelector("zdk-tabs");
    console.log("the selected tab is ",tabs.selected);
    tabs.selected = 2; // select the third tab

When a given tab is selected by programming, the component is updated auto-magically.

Creating a Tab is very simple as shown in the addTab function above. A tab is a "zdk-tab" tag with the property "heading" for the label.

Writing the "heading" property, automagically update the tab component.

    <zdk-tab heading="tab">
        you content here
    <zdk-tab>

