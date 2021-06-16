```java
import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.Graphics;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.IOException;

import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextArea;
import javax.swing.JTextField;

import org.mariadb.jdbc.credential.aws.AwsIamCredentialPlugin;

public class SearchView extends JFrame implements ActionListener {

	private JPanel leftPanel;
	private JPanel bigPanel;
	private JPanel smallPanel;
	private JPanel westPanel;
	private JPanel eastPanel;
	private JLabel subwayLabel;
	private JLabel searchLabel;
	private JTextField searchField;
	private JButton button, backButton;
	
	ImageIcon icon;

	public SearchView() {
		super("찾기");
		setDefaultCloseOperation(EXIT_ON_CLOSE);
		setSize(800, 800);
		setLocationRelativeTo(null);

		button = new JButton("search");
		button.addActionListener(this);
		backButton = new JButton("<-");
		backButton.addActionListener(new ActionListener() {

			@Override
			public void actionPerformed(ActionEvent e) {
				MainView Mainview = new MainView();
				Mainview.setVisible(true);
				Mainview.setLocationRelativeTo(null);

				dispose();

			}
		});

		searchField= new JTextField();
		
		icon = new ImageIcon("C:\\hwj\\_02_project\\mini_project\\src\\신촌.jpg");
		westPanel = new JPanel() {
			public void paintComponent(Graphics g) {
				g.drawImage(icon.getImage(),0, 0, null);
				setOpaque(false);
				super.paintComponent(g);
			}
		};
		westPanel.setPreferredSize(new Dimension(550,800));
		eastPanel = new JPanel();
		eastPanel.setPreferredSize(new Dimension(250,800));
	
		
//		
//		subwayLabel = new JLabel("subway picture");
//		subwayLabel.setOpaque(true);
//		subwayLabel.setBackground(Color.LIGHT_GRAY);

		searchLabel = new JLabel("지하철 역을 입력하세요:");

		smallPanel = new JPanel();
		smallPanel.setLayout(new BorderLayout());
		smallPanel.add(backButton, BorderLayout.WEST);
		// smallPanel.add(searchLabel, BorderLayout.WEST);
		smallPanel.add(searchField, BorderLayout.CENTER);
		smallPanel.add(button, BorderLayout.EAST);

		leftPanel = new JPanel();
		leftPanel.setLayout(new BorderLayout());

		leftPanel.add(westPanel, BorderLayout.CENTER);
		leftPanel.add(smallPanel, BorderLayout.NORTH);

		bigPanel = new JPanel();
		bigPanel.setLayout(new BorderLayout());
		bigPanel.add(leftPanel, BorderLayout.CENTER);
		bigPanel.add(eastPanel, BorderLayout.EAST);
		this.add(bigPanel);

		setVisible(true);

	}

	@Override
	public void actionPerformed(ActionEvent e) {
		if (searchField.getText().equals("신촌")) {
			double 위도 = 37.55514583255051;
			double 경도 = 126.93689753734925;
			try {
				Runtime.getRuntime().exec(new String[] { "C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe",
						String.format("https://map.kakao.com/link/map/%f,%f", 위도, 경도)

				});
			} catch (IOException e1) {
				e1.printStackTrace();
			}
		}
	}

//	public void paintComponent(Graphics g,JPanel panel) {
//		g.drawImage(icon.getImage(), 0, 0, null);
//		panel.setOpaque(false);
//		panel.paintComponents(g);
//	}
	

	public static void main(String[] args) {
		new SearchView();

	}

}
```
