~~~
LoginView
~~~

```java
import java.awt.Dimension;
import java.awt.Font;

import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;

public class LoginView extends JFrame {
	JLabel login, id, pw;
	JTextField idField, pwField;
	
	LoginView(){
		super("회원가입");
		setSize(new Dimension(800, 800));
		
		
		JPanel panel = new JPanel();
		panel.setSize(new Dimension(800,800));
		
		login = new JLabel("로그인");
		login.setFont(new Font("Magneto 굵게",Font.BOLD , 60));
		id = new JLabel(" 아이디  ");
		id.setFont(new Font("Magneto 굵게",Font.BOLD , 13));
		pw = new JLabel(" 패스워드 ");
		pw.setFont(new Font("Magneto 굵게",Font.BOLD , 13));
		
		idField = new JTextField();
		pwField = new JTextField();
		
		login.setBounds(250, 100, 300, 100 );
		id.setBounds(150, 250, 70, 40);
		pw.setBounds(150, 300, 70, 40);
		idField.setBounds(220, 250, 300, 40);
		pwField.setBounds(220, 300, 300, 40);
		
		panel.setLayout(null);
		panel.add(login);
		panel.add(id);
		panel.add(pw);
		panel.add(idField);
		panel.add(pwField);
		
		
		
		add(panel);
		setVisible(true);
	}
	public static void main(String[] args) {
		new LoginView();
	}

}
```
