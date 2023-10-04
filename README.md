# Fast food menu java-project
import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JScrollPane;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

import java.awt.Font;
import javax.swing.JButton;
import javax.swing.border.TitledBorder;
import javax.swing.JRadioButton;
import javax.swing.border.EtchedBorder;
import java.awt.Color;
import javax.swing.JCheckBox;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JTextField;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;

public class Mamamiapizzaria extends JFrame {

private JPanel contentPane;
private JTextField txtTotal;
private JRadioButton ibSmall;
private JRadioButton ibMedium;
private JRadioButton ibLarge;



/**
* Launch the application.
*/
public static void main(String[] args) {
EventQueue.invokeLater(new Runnable() {
public void run() {
try {
Mamamiapizzaria frame = new Mamamiapizzaria();
frame.setVisible(true);
} catch (Exception e) {
e.printStackTrace();
}
}
});
}

/**
* Create the frame.
*/
public Mamamiapizzaria() {
setTitle("Mama Mia Pizzaria");
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
setBounds(100, 100, 588, 479);
contentPane = new JPanel();
contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));

setContentPane(contentPane);
contentPane.setLayout(null);

JScrollPane scrollPane = new JScrollPane();
scrollPane.setBounds(223, 10, 4, 4);
contentPane.add(scrollPane);

JLabel lblNewLabel = new JLabel("Mama Mia Pizzaria");
lblNewLabel.setFont(new Font("Lucida Grande", Font.BOLD, 20));
lblNewLabel.setBounds(195, 10, 229, 16);
contentPane.add(lblNewLabel);

JLabel cbSmall = new JLabel("Small     ");
cbSmall.setBounds(24, 76, 97, 16);
contentPane.add(cbSmall);

JLabel cbMedium = new JLabel("Medium");
cbMedium.setBounds(24, 122, 61, 16);
contentPane.add(cbMedium);

JLabel cbLarge = new JLabel("Large");
cbLarge.setBounds(24, 177, 61, 16);
contentPane.add(cbLarge);

JLabel lblNewLabel_2 = new JLabel("$4.99");
lblNewLabel_2.setBounds(111, 76, 61, 16);
contentPane.add(lblNewLabel_2);

JLabel lblNewLabel_1_3 = new JLabel("$6.99");
lblNewLabel_1_3.setBounds(111, 122, 61, 16);
contentPane.add(lblNewLabel_1_3);

JLabel lblNewLabel_1_4 = new JLabel("$8.99");
lblNewLabel_1_4.setBounds(111, 177, 61, 16);
contentPane.add(lblNewLabel_1_4);

JLabel cbToppings = new JLabel("Toppings");
cbToppings.setBounds(24, 233, 61, 16);
contentPane.add(cbToppings);

JLabel lblNewLabel_1_6 = new JLabel("$0.50 each");
lblNewLabel_1_6.setBounds(111, 233, 97, 16);
contentPane.add(lblNewLabel_1_6);

JPanel panel = new JPanel();
panel.setBorder(new TitledBorder(null, "Size", TitledBorder.LEADING, TitledBorder.TOP, null, null));
panel.setBounds(229, 78, 119, 139);
contentPane.add(panel);

ibSmall = new JRadioButton("Small");
ibSmall.addMouseListener(new MouseAdapter() {
@Override
public void mouseClicked(MouseEvent e) {
if(ibSmall.isSelected()) {
ibMedium.setSelected(false);
ibLarge.setSelected(false);
}
if(ibMedium.isSelected()) {
ibSmall.setSelected(false);
ibLarge.setSelected(false);
}
if(ibLarge.isSelected()) {
ibSmall.setSelected(false);
ibMedium.setSelected(false);
}
}

});
panel.add(ibSmall);

JRadioButton ibMedium = new JRadioButton("Medium");
panel.add(ibMedium);

JRadioButton ibLarge = new JRadioButton("Large");
panel.add(ibLarge);

JPanel panel_1 = new JPanel();
panel_1.setBorder(new TitledBorder(new EtchedBorder(EtchedBorder.LOWERED, null, null), "Toppings", TitledBorder.LEADING, TitledBorder.TOP, null, new Color(0, 0, 0)));
panel_1.setBounds(360, 88, 181, 212);
contentPane.add(panel_1);

JCheckBox cbpepperoni = new JCheckBox("pepperoni");
panel_1.add(cbpepperoni);

JCheckBox cbitaliansausage = new JCheckBox("italian sausage");
panel_1.add(cbitaliansausage);

JCheckBox cbpineapple = new JCheckBox("pineapple");
panel_1.add(cbpineapple);

JCheckBox cbextracheese = new JCheckBox("Extra cheese");
panel_1.add(cbextracheese);

JCheckBox cbgreenpepper = new JCheckBox("green pepper");
panel_1.add(cbgreenpepper);

JCheckBox cbolives = new JCheckBox("olives");
panel_1.add(cbolives);

JButton btnNewButton = new JButton("calculate");
btnNewButton.addActionListener(new ActionListener() {
public void actionPerformed(ActionEvent e) {
double cost =0;
if (ibSmall.isSelected())
cost+=4.99;

if (ibMedium.isSelected())
cost+=6.99;

if (ibLarge.isSelected())
cost+=8.99;

if (cbpepperoni.isSelected())
cost+=0.50;

if (cbpineapple.isSelected())
cost+=0.50;
if (cbolives.isSelected())
cost+=0.50;
if (cbitaliansausage.isSelected())
cost+=0.50;
if (cbextracheese.isSelected())
cost+=0.50;

if (cbgreenpepper.isSelected())
cost+=0.50;
double Total=cost;
txtTotal.setText(""+Total);
JOptionPane.showMessageDialog(null, "your pizza costs" + cost);

}
});
btnNewButton.setBounds(24, 388, 117, 29);
contentPane.add(btnNewButton);

JButton btnExit = new JButton("exit");
btnExit.addActionListener(new ActionListener() {
public void actionPerformed(ActionEvent e) {
System.exit(0);

}
});
btnExit.setBounds(153, 388, 117, 29);
contentPane.add(btnExit);

JButton btnNewButton_1 = new JButton("Total");
btnNewButton_1.addActionListener(new ActionListener() {
public void actionPerformed(ActionEvent e) {

}
});
btnNewButton_1.setBounds(306, 384, 97, 36);
contentPane.add(btnNewButton_1);

txtTotal = new JTextField();
txtTotal.setBounds(411, 388, 130, 26);
contentPane.add(txtTotal);
txtTotal.setColumns(10);
}
}
