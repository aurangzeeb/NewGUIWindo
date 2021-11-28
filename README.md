# NewGUIWindo

// IN THIS PROJECT WE CREATING A SIMPLE GUI WINDOW PROGRAM 
//IN THE START IT WILL SHOW YOU ONE GUI WINDOW AND A BUTTON 
// WHEN YOU CLICK ON BUTTON IT WILL CREATE ANOTHER GUI WINDOW WITH SOME LABEL TEXT "HELLO SIR"

//It's Main Class 
public class Main {

	public static void main(String[] args) {
		
		MyFrame myframe = new MyFrame();
	}

}



import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;

public class MyFrame implements ActionListener {
	
	JFrame frame = new JFrame();            //OBJECT OF FRAME
  

	JButton myButton = new JButton("New Window");     //OBJECT OF BUTTON
	

	MyFrame(){                                //CONSTRUCTOR        
  

		myButton.setBounds(100, 150, 100, 50);        //BUTTON PRAMETERS
		myButton.setFocusable(false);
		myButton.addActionListener(this);
		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);       //FRAME PARAMETERS
		frame.setSize(420,420);
		frame.setVisible(true);
		frame.setLayout(null);
		frame.add(myButton);
	}
 //Method of ActionListener so we can make our Button responsive
	@Override
	public void actionPerformed(ActionEvent e) {
		
		if(e.getSource()==myButton) {
			frame.dispose();
			NewWindow window = new NewWindow();
		}
		
	}

}


//New Window Class 

import java.awt.Font;

import javax.swing.JFrame;
import javax.swing.JLabel;

public class NewWindow {

 
	JFrame frame = new JFrame();
  
	JLabel label = new JLabel("hello sir!");
	

	NewWindow(){
		
		label.setBounds(0,0,100,150);           // LABEL PARAMETERS
		label.setFont(new Font(null,Font.PLAIN,25));
		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(420,420);
		frame.setVisible(true);
		frame.setLayout(null);
		frame.add(label);
		
	}

}

