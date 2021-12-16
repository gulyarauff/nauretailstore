# nauretailstore
online app
//This is course project NAU-retail-store//
import java.awt.BorderLayout;

import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

import java.awt.Font;
import javax.swing.SwingConstants;
import javax.swing.JTextField;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JEditorPane;
import java.awt.Color;
import java.awt.Component;

public class MainFrame extends JFrame {

	private JPanel contentPane;
	private JTextField tfLoginAs;
	private JTextField tfUsername;
	private JTextField tfPassword;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					MainFrame frame = new MainFrame();
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
	public MainFrame() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 492, 454);
		contentPane = new JPanel();
		contentPane.setBackground(new Color(255, 228, 196));
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JLabel lblNewLabel = new JLabel("LOGIN");
		lblNewLabel.setHorizontalAlignment(SwingConstants.CENTER);
		lblNewLabel.setFont(new Font("Tahoma", Font.BOLD, 15));
		lblNewLabel.setBounds(155, 35, 117, 25);
		contentPane.add(lblNewLabel);
		
		JLabel lblNewLabel_1 = new JLabel("Login As");
		lblNewLabel_1.setHorizontalAlignment(SwingConstants.LEFT);
		lblNewLabel_1.setFont(new Font("Tahoma", Font.BOLD, 12));
		lblNewLabel_1.setBounds(41, 78, 70, 20);
		contentPane.add(lblNewLabel_1);
		
		tfLoginAs = new JTextField();
		tfLoginAs.setBounds(141, 81, 238, 20);
		contentPane.add(tfLoginAs);
		tfLoginAs.setColumns(10);
		
		JLabel lblNewLabel_2 = new JLabel("User name");
		lblNewLabel_2.setFont(new Font("Tahoma", Font.BOLD, 12));
		lblNewLabel_2.setBounds(41, 130, 70, 20);
		contentPane.add(lblNewLabel_2);
		
		tfUsername = new JTextField();
		tfUsername.setBounds(141, 131, 238, 20);
		contentPane.add(tfUsername);
		tfUsername.setColumns(10);
		
		JLabel lblNewLabel_3 = new JLabel("Password");
		lblNewLabel_3.setFont(new Font("Tahoma", Font.BOLD, 12));
		lblNewLabel_3.setBounds(41, 177, 70, 20);
		contentPane.add(lblNewLabel_3);
		
		tfPassword = new JTextField();
		tfPassword.setBounds(141, 178, 238, 20);
		contentPane.add(tfPassword);
		tfPassword.setColumns(10);
		
		JButton btnOK = new JButton("OK");
		btnOK.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				
				String loginAs=tfLoginAs.getText();
				String userName=tfUsername.getText();
				String password=tfPassword.getText();
				
				if (loginAs.equals("admin") && userName.equals("manager") && password.equals("12345")) 
				{
					JOptionPane.showMessageDialog(frame, "Successful login");
					
					Products product=new Products();
					product.setVisible(true);
				}
				else
				{
					JFrame frame=new JFrame ();
					JOptionPane.showMessageDialog(frame, "Invalid user or password");
				}
			}
		});
		btnOK.setBounds(148, 227, 89, 23);
		contentPane.add(btnOK);
		
		JButton btnCancel = new JButton("Cancel");
		btnCancel.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				tfLoginAs.setText("");
				tfUsername.setText("");
				tfPassword.setText("");
				
			}
		});
		btnCancel.setBounds(283, 227, 89, 23);
		contentPane.add(btnCancel);
		
		JLabel lblNewLabel_4 = new JLabel("NAU-retail store");
		lblNewLabel_4.setForeground(new Color(34, 139, 34));
		lblNewLabel_4.setToolTipText("");
		lblNewLabel_4.setFont(new Font("Lucida Calligraphy", Font.BOLD, 14));
		lblNewLabel_4.setBackground(new Color(255, 153, 255));
		lblNewLabel_4.setBounds(6, 2, 151, 38);
		contentPane.add(lblNewLabel_4);
	}
}

