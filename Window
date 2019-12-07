import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JScrollBar;

import java.awt.BorderLayout;
import javax.swing.JComboBox;
import javax.swing.JLabel;
import java.awt.Font;
import javax.swing.JTextField;
import javax.swing.JButton;
import java.awt.GridBagLayout;
import java.awt.GridBagConstraints;
import java.awt.Insets;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.text.ParseException;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.Scanner;

import javax.swing.DefaultComboBoxModel;
import javax.swing.SwingConstants;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.awt.Color;
public class Windows {

	private JFrame frmCurrencyConverter;
	private JTextField textField;
	private static double input,rate;
	private JLabel Time;
	final DateTimeFormatter dtf=DateTimeFormatter.ofPattern("yyyy-MM-dd  HH:mm:ss");
	static double crcy[]=new double[120];//
	
	static double crecy[]=new double[60] ;//exchange currency
	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
			
		Windows window = new Windows();
		window.getData();
		window.frmCurrencyConverter.setVisible(true);
		
		}
	/**
	 * Create the application.
	 */
	public Windows() {
		
		initialize();
		
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		String[] currency=new String[] 
				{"Argentine Peso",
				"Australian Dollar", 
				"Bahraini Dinar", 
				"Botswana Pula", 
				"Brazilian Real",  
				"Bruneian Dollar", 
				"Bulgarian Lev", 
				"Canadian Dollar", 
				"Chilean Peso", 
				"Chinese Yuan Renminbi", 
				"Colombian Peso", 
				"Croatian Kuna", 
				"Czech Koruna", 
				"Danish Krone", 
				"Emirati Dirham", 
				"Euro", 
				"Hong Kong Dollar", 
				"Hungarian Forint", 
				"Icelandic Krona", 
				"Indian Rupee", 
				"Indonesian Rupiah", 
				"Iranian Rial", 
				"Israeli Shekel", 
				"Japanese Yen", 
				"Kazakhstani Tenge", 
				"Kuwaiti Dinar", 
				"Libyan Dinar", 
				"Malaysian Ringgit", 
				"Mauritian Rupee", 
				"Mexican Peso", 
				"Nepalese Rupee", 
				"New Zealand Dollar", 
				"Norwegian Krone", 
				"Omani Rial", 
				"Pakistani Rupee", 
				"Philippine Peso", 
				"Polish Zloty", 
				"Qatari Riyal", 
				"Romanian New Leu", 
				"Russian Ruble", 
				"Saudi Arabian Riyal", 
				"Singapore Dollar", 
				"South African Rand", 
				"South Korean Won", 
				"Sri Lankan Rupee", 
				"Swedish Krona", 
				"Swiss Franc",
				"Taiwan New Dollar", 
				"Thai Baht", 
				"Trinidadian Dollar", 
				"Turkish Lira", 
				"British Pound",
				"Venezuelan Bolivar",
				"US Dollar"};

		frmCurrencyConverter = new JFrame();
		frmCurrencyConverter.setTitle("Currency Converter");
		frmCurrencyConverter.setBounds(100, 100, 869, 312);
		frmCurrencyConverter.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		JPanel panel = new JPanel();
		frmCurrencyConverter.getContentPane().add(panel, BorderLayout.CENTER);
		GridBagLayout gbl_panel = new GridBagLayout();
		gbl_panel.columnWidths = new int[]{32, 79, 57, 23, 11, 57, 116, 0};
		gbl_panel.rowHeights = new int[]{43, 25, 0, 0, 0, 0, 0, 0};
		gbl_panel.columnWeights = new double[]{0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, Double.MIN_VALUE};
		gbl_panel.rowWeights = new double[]{0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, Double.MIN_VALUE};
		panel.setLayout(gbl_panel);
		
		JLabel from = new JLabel("FROM");
		from.setFont(new Font("Tahoma", Font.PLAIN, 30));
		GridBagConstraints gbc_from = new GridBagConstraints();
		gbc_from.anchor = GridBagConstraints.WEST;
		gbc_from.insets = new Insets(0, 0, 5, 5);
		gbc_from.gridx = 1;
		gbc_from.gridy = 1;
		panel.add(from, gbc_from);
		
		JComboBox baseCurr_list = new JComboBox<String>();
		baseCurr_list.setForeground(Color.DARK_GRAY);
		JScrollBar pane = new JScrollBar();
		baseCurr_list.setModel(new DefaultComboBoxModel(currency));
		baseCurr_list.addItem(pane);
		baseCurr_list.setMaximumRowCount(52);
		baseCurr_list.setFont(new Font("Sitka Text", Font.BOLD, 20));
		GridBagConstraints gbc_baseCurr_list = new GridBagConstraints();
		gbc_baseCurr_list.fill = GridBagConstraints.HORIZONTAL;
		gbc_baseCurr_list.insets = new Insets(0, 0, 5, 5);
		gbc_baseCurr_list.gridx = 2;
		gbc_baseCurr_list.gridy = 1;
		panel.add(baseCurr_list, gbc_baseCurr_list);
		
		JLabel to = new JLabel("TO");
		to.setFont(new Font("Tahoma", Font.PLAIN, 30));
		GridBagConstraints gbc_to = new GridBagConstraints();
		gbc_to.anchor = GridBagConstraints.WEST;
		gbc_to.insets = new Insets(0, 0, 5, 5);
		gbc_to.gridwidth = 2;
		gbc_to.gridx = 3;
		gbc_to.gridy = 1;
		panel.add(to, gbc_to);
		
		JComboBox<String> ToCerr_list = new JComboBox<String>();
		ToCerr_list.setForeground(Color.BLUE);
		ToCerr_list.setModel(new DefaultComboBoxModel<String>(currency));
		ToCerr_list.setMaximumRowCount(52);
		ToCerr_list.setFont(new Font("Sitka Subheading", Font.BOLD, 20));
		GridBagConstraints gbc_ToCerr_list = new GridBagConstraints();
		gbc_ToCerr_list.insets = new Insets(0, 0, 5, 5);
		gbc_ToCerr_list.gridx = 5;
		gbc_ToCerr_list.gridy = 1;
		panel.add(ToCerr_list, gbc_ToCerr_list);
		
		JLabel amount = new JLabel("Amount:");
		amount.setFont(new Font("Tahoma", Font.BOLD, 19));
		amount.setHorizontalAlignment(SwingConstants.LEFT);
		GridBagConstraints gbc_amount = new GridBagConstraints();
		gbc_amount.insets = new Insets(0, 0, 5, 5);
		gbc_amount.gridx = 1;
		gbc_amount.gridy = 2;
		panel.add(amount, gbc_amount);
		
		textField = new JTextField();
		textField.setFont(new Font("Tahoma", Font.PLAIN, 22));
		textField.setText("0.0");
		textField.setHorizontalAlignment(SwingConstants.LEFT);
		GridBagConstraints input_amount = new GridBagConstraints();
		input_amount.gridwidth = 4;
		input_amount.insets = new Insets(0, 0, 5, 5);
		input_amount.fill = GridBagConstraints.HORIZONTAL;
		input_amount.gridx = 2;
		input_amount.gridy = 2;
		panel.add(textField, input_amount);
		textField.setColumns(10);
		
		JLabel Get = new JLabel("Get:");
		Get.setHorizontalAlignment(SwingConstants.CENTER);
		Get.setFont(new Font("Tahoma", Font.BOLD | Font.ITALIC, 19));
		GridBagConstraints gbc_Get = new GridBagConstraints();
		gbc_Get.insets = new Insets(0, 0, 5, 5);
		gbc_Get.gridx = 1;
		gbc_Get.gridy = 4;
		panel.add(Get, gbc_Get);
		
		JLabel output_amount = new JLabel("0.0");
		output_amount.setForeground(Color.RED);
		output_amount.setHorizontalAlignment(SwingConstants.LEFT);
		output_amount.setFont(new Font("Tahoma", Font.BOLD | Font.ITALIC, 20));
		GridBagConstraints gbc_output_amount = new GridBagConstraints();
		gbc_output_amount.gridwidth = 3;
		gbc_output_amount.fill = GridBagConstraints.HORIZONTAL;
		gbc_output_amount.anchor = GridBagConstraints.WEST;
		gbc_output_amount.insets = new Insets(0, 0, 5, 5);
		gbc_output_amount.gridx = 2;
		gbc_output_amount.gridy = 4;
		panel.add(output_amount, gbc_output_amount);
		
		JLabel lblNewLabel_1 = new JLabel("");
		lblNewLabel_1.setHorizontalAlignment(SwingConstants.LEFT);
		lblNewLabel_1.setFont(new Font("Tahoma", Font.BOLD | Font.ITALIC, 20));
		GridBagConstraints gbc_lblNewLabel_1 = new GridBagConstraints();
		gbc_lblNewLabel_1.insets = new Insets(0, 0, 5, 5);
		gbc_lblNewLabel_1.gridx = 5;
		gbc_lblNewLabel_1.gridy = 4;
		panel.add(lblNewLabel_1, gbc_lblNewLabel_1);
		JButton Reverse = new JButton("Reverse");
		Reverse.setMnemonic('r');		
		
		Reverse.addActionListener(new ActionListener() {
			int click=0;
			public void actionPerformed(ActionEvent arg0) {
				if(rate>0) {
					rate=1/rate;
					output_amount.setText(String.valueOf(rate*input));
					click++;
					if(click%2==1)
						{Reverse.setText("Reverse Back");
						lblNewLabel_1.setText(baseCurr_list.getSelectedItem().toString());
						}
					else 
						{Reverse.setText("Reverse");
						lblNewLabel_1.setText(ToCerr_list.getSelectedItem().toString());
						}
				}
			}
		});
		Reverse.setFont(new Font("Sylfaen", Font.BOLD, 20));
		GridBagConstraints gbc_Reverse = new GridBagConstraints();
		gbc_Reverse.insets = new Insets(0, 0, 5, 5);
		gbc_Reverse.gridx = 2;
		gbc_Reverse.gridy = 5;
		panel.add(Reverse, gbc_Reverse);
		
		JButton Update = new JButton(" Update ");
		Update.setMnemonic('u');
		Update.setFont(new Font("Sylfaen", Font.BOLD, 20));
		
		JButton Convert = new JButton("Convert ");
		Convert.setMnemonic('c');
		Convert.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				rate=crecy[ToCerr_list.getSelectedIndex()]/crecy[baseCurr_list.getSelectedIndex()];
				input=Double.parseDouble(textField.getText());
				if(rate<0||input<0) {
					output_amount.setText("Please enter a non-negative number.");
				}
				else 
					output_amount.setText(String.format("%.5f",rate*input));
			} });
		Convert.setFont(new Font("Times New Roman", Font.BOLD, 22));
		GridBagConstraints Convert_Pan = new GridBagConstraints();
		Convert_Pan.insets = new Insets(0, 0, 5, 5);
		Convert_Pan.gridx = 5;
		Convert_Pan.gridy = 5;
		panel.add(Convert, Convert_Pan);
		GridBagConstraints gbc_Update = new GridBagConstraints();
		gbc_Update.insets = new Insets(0, 0, 0, 5);
		gbc_Update.gridx = 1;
		gbc_Update.gridy = 6;
		panel.add(Update, gbc_Update);
		
		Time = new JLabel();
		Time.setForeground(new Color(0, 128, 0));
		Time.setBackground(Color.ORANGE);
		Time.setFont(new Font("Tahoma", Font.PLAIN, 18));
		
		Time.setText(LocalDateTime.now().format(dtf));
		GridBagConstraints TimePan = new GridBagConstraints();
		TimePan.insets = new Insets(0, 0, 0, 5);
		TimePan.gridx = 2;
		TimePan.gridy = 6;
		panel.add(Time, TimePan);
		
		Update.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				getData();
				Time.setText(LocalDateTime.now().format(dtf));
			} });
	}
	public void getData() {		
	int i=0;
	for(int l=0;l<120;l++)
		{
			if(l<60)
				crecy[l]=-1;
		crcy[l]=-1.0;
		}
			String inputLine = null;
			
			URL rates;
			try {
				rates = new URL("https://www.x-rates.com/table/?from=USD&amount=1");
				 BufferedReader in = new BufferedReader(
					     new InputStreamReader(rates.openStream()));				  
					     int count=0;
					     while ((inputLine = in.readLine()) != null&&count<456) {
					    	 count++;
					    	 if(count>189)
					         {	
					    		 inputLine =inputLine.replaceAll("[^0-9.]", "");
					    		 if(inputLine.matches(".*\\d.*"))
					    		 {crcy[i]=Double.parseDouble(inputLine.replace("..", ""));
					    		 if(i%2==0&&crcy[i]!=-1.0) {
					    			 if(i==0) {
					    				 crecy[0]=crcy[i];
					    			 }
					    			 else {
					    				 crecy[i/2]=crcy[i];
					    			 }
					    		 }
					    		 i++;}
					    		 
					         }							    	 
					        }

					     in.close();
					     double temp=crecy[50];
					     for(int a=49;a>13;a--) {/*correct sequence*/
					    	 crecy[a+1]=crecy[a];
					     }
					     crecy[14]=temp;
					     temp=crecy[25];
					     
					     for(int a=26;a<43;a++) {
					    	 crecy[a-1]=crecy[a];
					     }
					     crecy[42]=temp;
					     temp=crecy[42];
					     crecy[42]=crecy[43];
					     crecy[43]=temp;
					     int a=0;
					     for(;a<60;a++) {
					    	 if(crecy[a]==-1)
					    		 break;
					     }
					     crecy[a]=1.0;
			} catch (MalformedURLException e) {
				e.printStackTrace();
			} catch (IOException e) {						
				e.printStackTrace();
			}
		}
}
