# Real-Estate-application
 N&amp;R Real Estate application: At the beginning, the program will welcome visitors to the real estate then the program will show the menu that involves buying, rent, and other services including the price, and let the user book the desired number of estates for his family. In addition, the rese
code:
Page1:
package tryproject1;

import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.FlowLayout;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.HeadlessException;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

 public class Oop_pro extends JFrame {
     private JButton Exitbutton,contactButton,buyButton,InforButton,rentButton;
    //constructer for oop_pro to run app that we call it in login 
 public Oop_pro() throws HeadlessException {
        setTitle("Home Page");
        setSize(650, 490);
        setResizable(false);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(new BorderLayout(25,25));
        
        //------------------------------------
        JPanel panel = new JPanel();
        JPanel panelAll,p_R,p_B,p_C,p_Info,p,p_title1,p_title2_1,p_title2_2,p_titleALL,empty_panel,Exitpanel;
        panelAll = new JPanel(new GridLayout(2,2,20,15));
        p_titleALL = new JPanel(new GridLayout(4,1));
        Exitpanel = new JPanel(new FlowLayout(FlowLayout.CENTER));
        empty_panel = new JPanel();
        p_R = new JPanel();
        p_B = new JPanel();
        p_C = new JPanel();
        p_Info = new JPanel();
        p = new JPanel();
        p_title2_1 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_title2_2 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_title1 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        
        // the title
        JLabel title1 = new JLabel("N&R REAL ESTATE");
        title1.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,22));
        p_title1.add(title1);
        
        //Labels
        JLabel titel2_1 =new JLabel("We're delighted to have you here, to enhance your experience");
        titel2_1.setFont(new Font("Serif", Font.PLAIN, 18));
        JLabel titel2_2 = new JLabel("please take a moment to select the best suits your needs"); 
        titel2_2.setFont(new Font("Serif", Font.PLAIN, 18));
        p_title2_1.add(titel2_1);
        p_title2_2.add(titel2_2);
        p_titleALL.add(p_title1);
        p_titleALL.add(empty_panel);
        p_titleALL.add(p_title2_1);
        p_titleALL.add(p_title2_2);
       
   
        // RENT button 
         rentButton = new JButton("Rent");
         rentButton.setBackground(Color.BLACK);
         rentButton.setForeground(Color.WHITE);
         rentButton.setPreferredSize(new Dimension(150, 30));
         p_R.add(rentButton);
         
        //BUY button
        buyButton = new JButton("Buy");
        buyButton.setBackground(Color.BLACK);
        buyButton.setForeground(Color.WHITE);
        buyButton.setPreferredSize(new Dimension(150, 30));
        p_B.add(buyButton);
        
        //CONTACT button 
        contactButton = new JButton("Contact");
        contactButton.setBackground(Color.BLACK);
        contactButton.setForeground(Color.WHITE);
        contactButton.setPreferredSize(new Dimension(150, 30));
        p_C.add(contactButton);
        
        //User Information button
        InforButton = new JButton("User Informatiom");
        InforButton.setBackground(Color.BLACK);
        InforButton.setForeground(Color.WHITE);
        InforButton.setPreferredSize(new Dimension(150, 30));
        p_Info.add(InforButton);
        
        //Exit button
        Exitbutton = new JButton("Exit");
        Exitbutton.setBackground(Color.BLACK);
        Exitbutton.setForeground(Color.WHITE);
        Exitbutton.setPreferredSize(new Dimension(100, 30));
        Exitpanel.add(Exitbutton);
        
        //add all components to the gridLayout
        panelAll.add(p_R);
        panelAll.add(p_B);
        panelAll.add(p_C);
        panelAll.add(p_Info);
        p.add(panelAll);
        
        //add photo YOU NEED TO FIXT ITTTTTT!!!!!!! 
        JLabel background=new JLabel(new ImageIcon("WhatsApp Image 2023-11-12 at 9.14.20 PM.jpeg"));
        
        
        add(p,BorderLayout.CENTER);
        add(p_titleALL,BorderLayout.NORTH);
        add(Exitpanel,BorderLayout.SOUTH);
        
        // Add action listeners to the buttons 
        rentButton.addActionListener(new createSelectionActionListener());
        buyButton.addActionListener(new createSelectionActionListener());
        contactButton.addActionListener(new createSelectionActionListener());
        Exitbutton.addActionListener(new createSelectionActionListener());
        
    }
    
        //  ActionListener for RENT AND BUY 
    private class createSelectionActionListener implements ActionListener{
            @Override
            public void actionPerformed(ActionEvent e) {
               if(e.getSource()== Exitbutton){
                   dispose();
               }
               else if(e.getSource()== contactButton){
                   openContactWindow ContactWindow = new openContactWindow();
                   ContactWindow.setVisible(true);
                   dispose();
               }
               else if(e.getSource()== buyButton){
                   openBuyWindow BuyWindow = new openBuyWindow();
                   BuyWindow.setVisible(true);
                   dispose();
               }
               else if(e.getSource()== rentButton){
                   openRentWindow RentWindow = new openRentWindow();
                   RentWindow.setVisible(true);
                   dispose();
               }
            }
        };
    }

Page2:
package tryproject1;

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

public class openBuyWindow extends JFrame{
    private JLabel label1,label2,labelPictrue;
    private JButton Next_button,cancel_button;
    private JRadioButton R1,R2,R3;
    private JPanel p_label1,p_label2,p_button,p_radio,p_radioALL,p_labelALL,p_pictrue,p,p_empty;
    private ButtonGroup group;
    final int WINDOW_WIDTH = 650;
    final int WINDOW_HEIGHT = 490;

    public openBuyWindow() {
        setTitle("Buy Building");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout(25,25));
        setResizable(false);
        buildPage();
        
        add(p_labelALL, BorderLayout.NORTH);
        add(p, BorderLayout.CENTER);
        add(p_button,BorderLayout.SOUTH);
        setSize(WINDOW_WIDTH, WINDOW_HEIGHT);
        setLocationRelativeTo(null);
        setVisible(true);
    }

    private void buildPage() {
      //Panel
      p_label1 = new JPanel(new FlowLayout(FlowLayout.CENTER));
      p_label2 = new JPanel(new FlowLayout(FlowLayout.CENTER));
      p_button = new JPanel();
      p_radio = new JPanel();
      p_radioALL = new JPanel(new GridLayout(4,1));
      p_labelALL = new JPanel(new GridLayout(2,1));
      p_pictrue = new JPanel();
      p = new JPanel();
      p_empty = new JPanel();
      
      //Label
      label1 = new JLabel("N&R REAL ESTATE");
      label1.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,20));
      p_label1.add(label1);
      label2 = new JLabel("We have avilible building in :");
      label2.setFont(new Font("Serif",Font.PLAIN,18));
      p_label2.add(label2);
      p_labelALL.add(p_label1);
      p_labelALL.add(p_label2);
      
      //image
      ImageIcon image = new ImageIcon("home.jpg");
      labelPictrue = new JLabel(image);
      p_pictrue.add(labelPictrue);
      
      
      //Button
      Next_button = new JButton("Next");
      Next_button.setBackground(Color.BLACK);
      Next_button.setForeground(Color.WHITE);
      Next_button.setPreferredSize(new Dimension(150, 30));
      p_button.add(Next_button);
      cancel_button = new JButton("Cancel");
      cancel_button.setBackground(Color.BLACK);
      cancel_button.setForeground(Color.WHITE);
      cancel_button.setPreferredSize(new Dimension(150, 30));
      p_button.add(cancel_button);
      
      //Radio
      R1 = new JRadioButton("Albastien district :1,000,000SR");
      R1.setFont(new Font("Serif",Font.PLAIN,16) );
      R2 = new JRadioButton("AlHamdani district :950,000SR");
      R2.setFont(new Font("Serif",Font.PLAIN,16) );
      R3 = new JRadioButton("Alnaim district :1,000,000SR");
      R3.setFont(new Font("Serif",Font.PLAIN,16) );
      p_radio.add(R1);
      p_radio.add(R2);
      p_radio.add(R3);
      
      //ButtonGroup
      group = new ButtonGroup();
      group.add(R1);
      group.add(R2);
      group.add(R3);
      
      p_radioALL.add(p_empty);
      p_radioALL.add(R1);
      p_radioALL.add(R2);
      p_radioALL.add(R3);
      p.add(p_radioALL);
      
      //ActionListener
     cancel_button.addActionListener(new Action());
     Next_button.addActionListener(new Action());
    }
    private class Action implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if(e.getSource()== cancel_button){
                Oop_pro oopProWindow = new Oop_pro();
                oopProWindow.setVisible(true);
                dispose();
            }
            else if(e.getSource()== Next_button){
                ThankyouWindow thank = new ThankyouWindow();
                thank.setVisible(true);
                dispose();
            }
        }
   
    }
   
    
}

package tryproject1;

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

Page3:
public class openContactWindow extends JFrame {
 private JPanel p_label1,p_label2,p_label3,p_label4,p_label5,contactPanel_titleALL_1,panel_picture;
 private JPanel contactPanel_titleALL_2,contactPanel_Button,p1,p2,p_empty1,p_empty2,p_empty3;
 private JLabel label1,label2,label3,label4,label5,iconLabel;
 private JButton closeButton;
 final int WINDOW_WIDTH = 650;
 final int WINDOW_HEIGHT = 490;

    public openContactWindow() {
        setTitle("Contact");
        setSize(650, 490);
        setResizable(false);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(new BorderLayout());
        buildPage();
        add(p1,BorderLayout.NORTH);
        add(p2,BorderLayout.CENTER);
        add(panel_picture,BorderLayout.WEST);
        add(contactPanel_Button,BorderLayout.SOUTH);
        setVisible(true);
    }    

    private void buildPage() {
        //panels
        p_label1 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_label2 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_label3 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_label4 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        p_label5 = new JPanel(new FlowLayout(FlowLayout.CENTER));
        contactPanel_titleALL_1 = new JPanel(new GridLayout(3,1));
        contactPanel_titleALL_2= new JPanel(new GridLayout(5,1));
        contactPanel_Button = new JPanel(new FlowLayout(FlowLayout.CENTER));
        panel_picture= new JPanel(new FlowLayout(FlowLayout.CENTER));
        p1 = new JPanel();
        p2 = new JPanel();
        p_empty1 = new JPanel();
        p_empty2 = new JPanel();
        p_empty3 = new JPanel();
        
        
        //-----Labels-----
        //Title_1
        label1 = new JLabel("N&R REAL ESTATE");
        label1.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,22));
        p_label1.add(label1);
        label2 = new JLabel("   Contact Information");
        label2.setFont(new Font("Serif",Font.PLAIN,20));
        p_label2.add(label2);
        contactPanel_titleALL_1.add(label1);
        contactPanel_titleALL_1.add(p_empty1);
        contactPanel_titleALL_1.add(label2);
        p1.add(contactPanel_titleALL_1);
        
        //Title_2
        label3 = new JLabel("Email: N&R@gmail.com");
        label3.setFont(new Font("Serif", Font.PLAIN, 18));
        p_label3.add(label3);
        label4 = new JLabel("Phone Number: +966598342654");
        label4.setFont(new Font("Serif", Font.PLAIN, 18));
        p_label4.add(label4);
        label5 = new JLabel("Address: Jeddah,Al-Nuzha district");
        label5.setFont(new Font("Serif", Font.PLAIN, 18));
        p_label5.add(label5);
        contactPanel_titleALL_2.add(p_empty2);
        contactPanel_titleALL_2.add(p_empty3);
        contactPanel_titleALL_2.add(label3);
        contactPanel_titleALL_2.add(label4);
        contactPanel_titleALL_2.add(label5);
        p2.add(contactPanel_titleALL_2);
        
        //image
        iconLabel = new JLabel();
        ImageIcon logo = new ImageIcon("ho.jpg");
        iconLabel.setIcon(logo);
        panel_picture.add(iconLabel);

        
        //Button which is in contact window
        closeButton = new JButton("Close");
        closeButton.setBackground(Color.BLACK);
        closeButton.setForeground(Color.WHITE);
        closeButton.setPreferredSize(new Dimension(100, 30));
        contactPanel_Button.add(closeButton);
        
        closeButton.addActionListener(new Action());   
    }
    private class Action implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if(e.getSource()== closeButton){
                Oop_pro oopProWindow = new Oop_pro();
                oopProWindow.setVisible(true);
                dispose();
            }
        }
   
    }}
 Page4: 
package tryproject1;

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;


public class openRentWindow extends JFrame{
    private JLabel label1,label2,labelPictrue,label3,label4;
    private JButton Next_button,cancel_button;
    private JRadioButton R1,R2,R3;
    private JCheckBox Check1_Service,Check2_Service,Check3_Service;
    private JPanel p_label1,p_label2,p_button,p_radioALL,p_labelALL,p_pictrue,p,p_label3,p_label4,p_txt,p_serviese;
    private ButtonGroup group1;
    private JTextField text;
    final int WINDOW_WIDTH = 650;
    final int WINDOW_HEIGHT = 490;

    public openRentWindow() {
        setTitle("Rent Building");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout(25,25));
        setResizable(false);
        buildPage();
        
        add(p_labelALL, BorderLayout.NORTH);
        add(p, BorderLayout.CENTER);
        add(p_button,BorderLayout.SOUTH);
        setSize(WINDOW_WIDTH, WINDOW_HEIGHT);
        setLocationRelativeTo(null);
        setVisible(true);
    }

    private void buildPage() {
      //Panel
      p_label1 = new JPanel(new FlowLayout(FlowLayout.CENTER));
      p_label2 = new JPanel(new FlowLayout(FlowLayout.CENTER));
      p_label3 = new JPanel(new FlowLayout(FlowLayout.CENTER));
      p_button = new JPanel();
      p_radioALL = new JPanel(new GridLayout(8,1));
      p_labelALL = new JPanel(new GridLayout(2,1));
      p_pictrue = new JPanel();
      p = new JPanel();//GridLayout ذي ترتبها
      p_txt = new JPanel();
      p_label4 = new JPanel();
      p_serviese = new JPanel(new FlowLayout(FlowLayout.CENTER));
      
      //Text
      text = new JTextField(20);
      p_txt.add(text);
      
      //Label
      label1 = new JLabel("N&R REAL ESTATE");
      label1.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,20));
      p_label1.add(label1);
      label2 = new JLabel("We have avilible building in :");
      label2.setFont(new Font("Serif",Font.PLAIN,18));
      p_label2.add(label2);
      p_labelALL.add(p_label1);
      p_labelALL.add(p_label2);
      label3 = new JLabel("How many years you want to rent:");
      label3.setFont(new Font("Serif",Font.PLAIN,16));
      p_label3.add(label3);
      label4 = new JLabel("Our property provieds services,including water and electrcity services:");
      label4.setFont(new Font("Serif",Font.PLAIN,16));
      p_label4.add(label4);
      
      
      //Button
      Next_button = new JButton("Next");
      Next_button.setBackground(Color.BLACK);
      Next_button.setForeground(Color.WHITE);
      Next_button.setPreferredSize(new Dimension(150, 30));
      p_button.add(Next_button);
      cancel_button = new JButton("Cancel");
      cancel_button.setBackground(Color.BLACK);
      cancel_button.setForeground(Color.WHITE);
      cancel_button.setPreferredSize(new Dimension(150, 30));
      p_button.add(cancel_button);
      
      //Radio
      R1 = new JRadioButton("Albastien district: 30,000 SR ");
      R1.setFont(new Font("Serif",Font.PLAIN,16) );
      R2 = new JRadioButton("AlRawdh district: 35,000 SR ");
      R2.setFont(new Font("Serif",Font.PLAIN,16) );
      R3 = new JRadioButton("Alnaim district: 19,000 SR ");
      R3.setFont(new Font("Serif",Font.PLAIN,16) );
      
      //CheckBox
      Check1_Service = new JCheckBox("Water Service");
      Check1_Service.setFont(new Font("Serif",Font.PLAIN,16) );
      Check2_Service = new JCheckBox("Electrcity Service");
      Check2_Service.setFont(new Font("Serif",Font.PLAIN,16) );
      Check3_Service = new JCheckBox("None");
      Check3_Service.setFont(new Font("Serif",Font.PLAIN,16) );
      p_serviese.add(Check1_Service);
      p_serviese.add(Check2_Service);
      p_serviese.add(Check3_Service);
       
      //ButtonGroup
      group1 = new ButtonGroup();
      group1.add(R1);
      group1.add(R2);
      group1.add(R3);
      
     
      p_radioALL.add(R1);
      p_radioALL.add(R2);
      p_radioALL.add(R3);
      p_radioALL.add(p_label3);
      p_radioALL.add(p_txt);
      p_radioALL.add(p_label4);
      p_radioALL.add(p_label4);
      p_radioALL.add(p_serviese);
      p.add(p_radioALL);
      
      //ActionListener
       cancel_button.addActionListener(new Action());
       Next_button.addActionListener(new Action());
    }
    private class Action implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if(e.getSource()== cancel_button){
                Oop_pro oopProWindow = new Oop_pro();
                oopProWindow.setVisible(true);
                dispose();
            }
            else if(e.getSource()== Next_button){
                ThankyouWindow thank = new ThankyouWindow();
                thank.setVisible(true);
                dispose();
        }
   
    }
      
    }}
   
Page5:
package tryproject1;

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;


public class ThankyouWindow extends JFrame{
 private JLabel label1,label2,label3;
 private JButton Done_button,file_button;
 //p_label --> for all the label in the north 
 //p_button --> for the done button in the south
 //p1 ---> to arange the gridlayout 
 private JPanel p_label,p_center,p_button,p_file,p1,p2,p3,p4,p5,p_label1,p_label2,p_label3;
 private final int WINDOW_WIDTH = 650;
 private final int WINDOW_HEIGHT = 490;
 
    public ThankyouWindow() {
        setTitle("Thank You");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout(25,25));
        setResizable(false);
        buildPage();
        //add
        add(p_label,BorderLayout.NORTH);
        add(p_button,BorderLayout.SOUTH);
        add(p1,BorderLayout.CENTER);
        add(p4,BorderLayout.WEST);
        add(p5,BorderLayout.EAST);
        setSize(WINDOW_WIDTH, WINDOW_HEIGHT);
        setLocationRelativeTo(null);
        setVisible(true);
    }

    private void buildPage() {
        
    //panel
    p_label = new JPanel(new GridLayout(3,1));
    p_button = new JPanel(new FlowLayout(FlowLayout.CENTER));
    p_center = new JPanel(new GridLayout(3,1));
    p_file = new JPanel(new FlowLayout(FlowLayout.CENTER));
    p1 = new JPanel();
    p2 = new JPanel();
    p3 = new JPanel();
    p4 = new JPanel();
    p5 = new JPanel();
    p_label1 = new JPanel();
    p_label2 = new JPanel();
    p_label3 = new JPanel();
    
    
    //Label
     label1 = new JLabel("N&R REAL ESTATE");
     label1.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,22));
     p_label1.add(label1);
     label2 = new JLabel("Thank You For Choosing us");
     label2.setFont(new Font("Serif",Font.TYPE1_FONT,20));
     p_label2.add(label2);
     p_label.add(p_label1);
     p_label.add(p3);
     p_label.add(p_label2);
     label3 = new JLabel("The Receipt");
     label3.setFont(new Font("Serif",Font.PLAIN,18));
     p_label3.add(label3);
     
     //Button 
     Done_button = new JButton("Done");
     Done_button.setBackground(Color.BLACK);
     Done_button.setForeground(Color.WHITE);
     Done_button.setPreferredSize(new Dimension(150, 30));
     Done_button.addActionListener(new Action());
     p_button.add(Done_button);
     
     file_button = new JButton("Save Receipt");
     file_button.setBackground(Color.BLACK);
     file_button.setForeground(Color.WHITE);
     file_button.setPreferredSize(new Dimension(150, 30));
     file_button.addActionListener(new Action());
     p_file.add(file_button);
     
     //---------------
     p_center.add(p2);
     p_center.add(p_label3);
     p_center.add(p_file);
     p1.setBorder(BorderFactory.createLineBorder(Color.DARK_GRAY, 1));
     p1.add(p_center);
    }
    
     private class Action implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if(e.getSource()== Done_button){
                Oop_pro oopProWindow = new Oop_pro();
                oopProWindow.setVisible(true);
                dispose();
        }
   
    }
   
    
}}
 Page6:
package tryproject1;


import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.FlowLayout;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

public class TryProject1 extends JFrame{
    JLabel iconLabel, FullnameLabel, IDlablel, phonelabel, adlabel,tiLabel;
    JTextField Name, ID, phnum, address;
    JButton Start;
    JPanel panel1, panel_Name, panel_ID, panel_phone,panel_AD,panelB,panelTitel,panelALL,panel_picture;

    final int WINDOW_WIDTH = 650;
    final int WINDOW_HEIGHT = 490;

    public TryProject1(){

        setTitle("Login Page");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout(25,25));
        buildPage();
        add(panelTitel,BorderLayout.NORTH);
        add(panelALL,BorderLayout.CENTER);
        add(panelB,BorderLayout.SOUTH);
        add(panel_picture,BorderLayout.WEST);
        setSize(WINDOW_WIDTH, WINDOW_HEIGHT);
        setResizable(false);
        setLocationRelativeTo(null);
        setVisible(true);

    }
public void buildPage() {
    //panel
    panel1 = new JPanel();
    panel1.setLayout(new GridLayout(4,1));
    panel_Name = new JPanel();
    panel_ID = new JPanel();
    panel_phone = new JPanel();
    panel_AD = new JPanel();
    panelB = new JPanel();
    panelTitel = new JPanel();
    panelALL= new JPanel();
    panel_picture= new JPanel(new FlowLayout(FlowLayout.CENTER));
    
    //image
    iconLabel = new JLabel();
    ImageIcon logo = new ImageIcon("grgr.jpg");
    iconLabel.setIcon(logo);
    panel_picture.add(iconLabel);
    
    //Label
    tiLabel = new JLabel("WELCOME TO N&R REAL ESTATE");
    tiLabel.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,24));
    FullnameLabel = new JLabel("Full Name:          ");
    IDlablel = new JLabel("National ID:         ");
    phonelabel = new JLabel("Phone Number:  ");
    adlabel = new JLabel("Address:             ");
    
    //text field
    Name = new JTextField(20);
    ID = new JTextField(20);
    phnum = new JTextField(20);
    address = new JTextField(20);
    
    //-------------------------------
    panel_Name.add(FullnameLabel);
    panel_Name.add(Name);
    panel1.add(panel_Name);
    panel_ID.add(IDlablel);
    panel_ID.add(ID);
    panel1.add(panel_ID);
    panel_phone.add(phonelabel);
    panel_phone.add(phnum);
    panel1.add(panel_phone);
    panel_AD.add(adlabel);
    panel_AD.add(address);
    panel1.add(panel_AD);
    panelALL.add(panel1);
   
    //-------------------------------
    panelTitel.add(tiLabel);
    
    //button
    Start = new JButton("Start");
    Start.setPreferredSize(new Dimension(150, 30));
    Start.setForeground(Color.WHITE);
    Start.setBackground(Color.BLACK);
    Start.addActionListener(new StartA());
    panelB.add(Start);

    
    //----Menu-----
    JMenuBar MenuBar = new JMenuBar();
    JMenu filemenu = new JMenu("File");
    JMenuItem item1 = new JMenuItem("Home Page");
    JMenuItem item2 = new JMenuItem("Exit");
    filemenu.add(item1);
    filemenu.add(item2);
    MenuBar.add(filemenu);
    setJMenuBar(MenuBar);
}

    // To get another Booking window
    private class StartA implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        // Create an instance of the oop_pro class
        Oop_pro oopProWindow = new Oop_pro();

        // Make the oop_pro window visible
        oopProWindow.setVisible(true);

        // Close the current Login window
        dispose();
    }
}


    public static void main(String[] args) {

        TryProject1 n = new TryProject1();
    }
}
  
