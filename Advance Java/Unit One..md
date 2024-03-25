
1. What is applet? Explain its life cycle?
   => Applet is a java library to write programs for the web. It mainly uses web browsers and applet viewers to display code output. 
   => Applet renders in client side. 
   => There are two methods to implement Applet. 
	   1. AWT(Abstract Window Toolkit)
	   2. JApplet (In Swing package)

	**Life Cycle of applet**
	- Applet Life consist of 4 phases as show in diagram below.
	 
	 - ![[Pasted image 20240323183138.png]]
	   1. `init()`  => First time and only that time will get invoked. Web browser runs init method within the applet.
	   2. `start()` => Immediately invoked  after init method. The actual code gets initiated. It is also gets invoked  when maximised moved from window to window in a web browser. 
	   3. `stop()` => Stops execution. invoked when minimised, when maximised start method invoked again.
	   4. `Destroy()` => When work is done. when applet window is closed or closing the tab in browser. Memory of applet is destroyed. 
2. Explain HTML APPLET tag and Passing parameter to Applet with the help of suitable example?
	=> HTML applet tag is used to render the content of applet code base on to the web browser. 
	
	Attributes :- 
		1. `code`:- points to the class of applet code. 
		2. `width`:- sets the width of a window on browser.
		3. `heigth`:- sets height. 			
		"note- height and width are specified in pixels."
		
	example:-  
		```<applet code="MyApplet.class" width="300" height="200"> Your browser doesn't support Java. </applet>```
3. Explain getDocumentBase() and getCodeBase() with the help of example?
   => 
   1. getDocumentBase() :- This gives URL to the folder where html document containing applet is located.
   2. getCodeBase():- gives URL to the folder where applet class is store. 
        
      
      **![](https://lh7-us.googleusercontent.com/MJ7lWJAO-ef9i2jO4GhuDeduDm3sO674l2TTPEr33RiLslnrALuZZgB5Reg3dKey-Dt2Lt2YXnmWm58MdDS-UkkZ-5TlJDzMQG62xJiQ7eTAgI5M7Xe6Nn9uKIFQ_4YxNqv7Qurlb-f_cNvpc0VXDVt32uC8Oz1f=s2048)**
4. What is J Applet, Icons and Labels Text Fields Buttons, Combo Boxes? 
   =>
    1. JApplet is top level swing container. `add()` method is use to add components into JApplet. It has more functionallity than normal Applet.
	   eg: - 
		   	```Conatainer contentPane = myApplet.getContentPane();
			JButton myButton = new JButton("Click Me!");
			 contentPane.add(myButton);```
	2. Icons : - Icons are small graphical images used to represent various entities or actions within a GUI.
		    eg.
		     ```import javax.swing.ImageIcon;
				import javax.swing.JFrame;
				import javax.swing.JLabel;
				public class IconExample extends JApplet{
					public static void main(String[] args){
						ImageIcon icon = new ImageIcon("icon.png");
						JLabel label = new JLabel(icon);
						JFrame frame = new JFrame();
						frame.add(label);
						frame.pack();
						frame.setVisible(true);
					} 
				}```
	3. Labels:- They are used to display text or images to provide description or info about other components. 
	   eg. 
		   ```import java.awt.Frame;
			import java.awt.Label;

			public class LabelExample extends JApplet {
			    public static void main(String[] args) {
			        Frame frame = new Frame("Label Example");
			        Label label = new Label("This is a label");
			        frame.add(label);
		        frame.setSize(200, 100);
		        frame.setVisible(true);
		    }
		}```
	4. Text Fields: - Allows user to input single line text data. 
	   eg. 
		   ```import java.awt.Frame; 
		   import java.awt.TextField;
		   public class TextFieldExample extends JApplet{
			   public static void main(String[] args){
				   Frame frame = new Frame("Text Field");
				   TextField textField = new TextField("Enter text here");
				   frame.add(textField);
				   frame.setSize(300,100);
				   frame.setVisible(true);
				}
		   }
	5. Buttons :- User  click to trigger an action or perform a task.
	   eg.  
		   ```import java.swing.JButton;
		   import java.swing.JFrame;
		   public class ButtonExample extends JApplet{
			   public static void main(String[] args){
				   JFrame frame = new JFrame("Button Example");
				   JButton button = new JButton("Click Me");
				   frame.add(button);
				   frame.setSize(200,100);
				   frame.setVisible(true);
			   }
		   }
	6. Combo Boxes : - Combo Boxes are GUI components which makes drop down list with an editable text field, allowing users to select from predefined options or input custom data.
	   eg. 
		   ```import javax.swing.JComboBox;
		   import javax.swing.JFrame;
		   public class ComboBoxExample extends JApplet{
			   public static void main(String[] args){
				   JFrame frame = new JFrame("Combo Box Example");
				   String[] options = {"Option 1","Option 2","Option 3"};
				   J
			   }
		   }
5.  What is Checkboxes, Tabbed Panes, Scroll Panes and Trees:
	Tables
	=> 
	Checkboxes are GUI components  that allow users to select one or more options from a list of choices by clicking an small boxes. To use import javax.swing.JCheckBox;
	eg.
		 ```import javax.swing.JCheckBox;
		import javax.swing.JFrame;
		import javax.swing.JPanel;
		public class CheckBoxExample extends JApplet{
			public static void main(String[] args){
				JFrame frame = new JFrame("Checkbox Example");
				JPanel panel = new JPanel();
				JCheckBox checkBox1 = new JCheckBox("Option 1");
				JCheckBox checkBox2 = new JCheckBox("Option 2");
				panel.add(checkBox1);
				panel.add(checkBox2);
				frame.add(panel);
				frame.setSize(300,200);
				frame.setVisible(true);
			}
		}```
6. Define applet. Write program to create an applet to display any message.
   =>   
	An applet is a Java program that is designed to be embedded within an HTML page and executed by a web browser's Java Virtual Machine (JVM). Applets provide a way to dynamically add interactivity and multimedia content to web pages.
		```import java.applet.Applet;
		import java.awt.Graphics;
		public class MessageApplet extends Applet {
		    public void paint(Graphics g) {
	        g.drawString("Hello, World!", 20, 20);
		    }
	    }``` 
7. List and explain applet tags. Explain the PARAM tag of applet
	with suitable diagram.
	=> Parameters are specified using the "name" and "value" attributes within the <param>tag. It allows customizing the behavior of the applet by passing values that the applet can use during initialization. Parameters are specified using the "name" and "value" attributes within the <param> tag.
	```<applet code="MyApplet.class" width="300" height="200"> <param name="message" value="Hello, World!"> Your browser doesn't support Java. </applet>``` 
8. What are limitations of AWT?
   => 1. Limited Components.
	2. Heavy resource hungry
	3. Lack of features.
	4. Lack of customisation options. 