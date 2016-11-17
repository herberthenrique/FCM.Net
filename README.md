# FCM.Net
Biblioteca para facilitar envio de **Push Notification** usando o **Firebase Cloud Messaging** do **Google**

Essa biblioteca foi escrita seguindo a documentação do próprio Google (https://firebase.google.com/docs/cloud-messaging/) com o intuito de facilitar o envio de mensagens a partir de um server app / desktop app (Console Application, Asp.Net, Windows Forms, WPF, etc).

##Exemplo de envio

```csharp
            var registrationId = "ID gerado quando o device é registrado no FCM";
            var serverKey = "acesse https://console.firebase.google.com/project/MY_PROJECT/settings/cloudmessaging";

            var sender = new Sender(serverKey);
            var message = new Message
            {
                RegistrationIds = new List<string> { registrationId }, //Pode-se passar uma lista de devices...
                Notification = new Notification
                {
                    Title = "FCM.Net :)",
                    Body = $"Olá Mundo!"
                }
            };
            var result = await sender.SendAsync(message);
```
Para saber mais sobre como montar sua notificação acesse https://firebase.google.com/docs/cloud-messaging/http-server-ref#table1.