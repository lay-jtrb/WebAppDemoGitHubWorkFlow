            try
            {
                using (var client = new System.Net.Mail.SmtpClient("email-smtp.ap-southeast-1.amazonaws.com", 25))
                {
                  
                    client.Credentials = new System.Net.NetworkCredential("AKIAQ3EGSYRWHVCWKNVP", "BCh6tkUmEQjbZG5XBWS+2vj2Q+Tle67SKcLniirdYhGg");
                    client.EnableSsl = false;

                    var mailMessage = new System.Net.Mail.MailMessage
                    {
                        //From = new System.Net.Mail.MailAddress("ronvanda99@gmail.com"),
                        From = new System.Net.Mail.MailAddress("lylay.it.kh855@gmail.com"),
                        Subject = "Your Subject",
                        Body = "Your Email Body",
                        IsBodyHtml = true
                    };

                    mailMessage.To.Add("ronvanda99@gmail.com");

                    client.Send(mailMessage);
                }

            }
            catch (Exception ex)
            {
                Console.WriteLine("Error sending email: " + ex.Message);
            }
