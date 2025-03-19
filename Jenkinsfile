pipeline {
    agent any
    stages {
        stage('Send Email Manually') {
            steps {
                script {
                    // Required imports
                    import javax.mail.*
                    import javax.mail.internet.*
                    import java.util.Properties

                    def props = new Properties()
                    props.put("mail.smtp.host", "smtp.gmail.com")
                    props.put("mail.smtp.port", "465")
                    props.put("mail.smtp.auth", "true")
                    props.put("mail.smtp.socketFactory.port", "465")
                    props.put("mail.smtp.socketFactory.class", "javax.net.ssl.SSLSocketFactory")

                    def session = Session.getInstance(props,
                        new Authenticator() {
                            protected PasswordAuthentication getPasswordAuthentication() {
                                return new PasswordAuthentication("xr045jss@gmail.com", "wwmifcolcxwgnylm")
                            }
                        }
                    )

                    def message = new MimeMessage(session)
                    message.setFrom(new InternetAddress("xr045jss@gmail.com"))
                    message.setRecipients(Message.RecipientType.TO, InternetAddress.parse("simranpreetkaur23105@gmail.com"))
                    message.setSubject("Groovy Mail from Jenkins")
                    message.setText("This is a manual email sent from a Jenkins pipeline using Groovy!")

                    Transport.send(message)
                    echo "Email sent successfully via Groovy SMTP"
                }
            }
        }
    }
}
