---
title: Настройка использования фотографий высокого разрешения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: Сводка. Настройка использования фотографий высокого разрешения в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online и Skype для бизнеса Server.
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834009"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Настройка использования фотографий высокого разрешения в Skype для бизнеса Server
 
**Сводка:** Настройка использования фотографий высокого разрешения в Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online и Skype для бизнеса Server.
  
В Skype для бизнеса Server фотографии можно хранить в почтовом ящике пользователя Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 или Exchange Online, что позволяет фотографии размером до 648 пикселей на 648 пикселей. Кроме того, Exchange Server могут автоматически по мере необходимости реанимировать эти фотографии для использования в разных продуктах. Как правило, используются фотографии трех размеров и разрешений, которые перечислены ниже.
  
- Размер 64 пикселя на 64 пикселя— размер, используемый для атрибута thumbnailPhoto Active Directory. Если вы загрузите фотографию в Exchange Server, Exchange автоматически создаст версию этой фотографии размером 64 на 64 пикселя и обнодит атрибут thumbnailPhoto пользователя. Обратите внимание, что обратное не так: если вручную обновить атрибут thumbnailPhoto в Active Directory, фотография в почтовом ящике Exchange пользователя не будет автоматически обновляться.
    
- 96 пикселей по 96 пикселей для использования в Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype для бизнеса Web App и Skype для бизнеса.
    
- 648 пикселей на 648 пикселей для использования в Skype для бизнеса и Skype для бизнеса Web App Skype для бизнеса Web App.
    
> [!NOTE]
> Если у вас есть ресурсы, рекомендуется отправить 648 фотографий x 648; обеспечивает максимальное разрешение и оптимальное качество изображения в любом из приложений Office 2013. Каждая фотография JPEG размером 648 x 648 и глубиной 24 бита приводит к размеру файла примерно 240 килобайт. Это значит, что для каждых 4 пользовательских фотографий потребуется примерно 1 мегабайт дискового пространства. 
  
Фотографии высокого разрешения, доступ к которым можно получить с помощью веб-служб Exchange, могут загружать пользователи, работающие с Outlook 2013 Web App; пользователям разрешено обновлять только собственные фотографии. Администраторы, однако, могут обновить фотографию для любого пользователя с помощью командной Windows PowerShell Exchange и следующих команд:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Первая команда в предыдущем примере использует командлет для чтения содержимого файла C:\Photos\Kenmyer.jpg и хранения этих данных в переменной с именем `Get-Content` $photo. Во второй команде командлет Exchange используется для отправки фотографии и прикрепления этой фотографии к учетной записи `Set-UserPhoto` пользователя Ken Myer.
  
> [!NOTE]
> В данном примере в качестве идентификатора учетной записи используется отображаемое имя пользователя Ken Myer в Active Directory. Для ссылки на учетную запись пользователя можно использовать и другие идентификаторы, например, SMTP-адрес пользователя или имя участника-пользователя. Дополнительные сведения см. в документации по Set-UserPhoto [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) управления
  
Отправка фотографии не означает, что она будет автоматически назначена учетной записи пользователя Ken Myer. После отправки фотография просто будет отображаться в режиме предварительного просмотра на странице параметров Outlook Web App. Чтобы назначить фотографию учетной записи, пользователь должен нажать кнопку **Сохранить** на странице параметров или же администратор должен выполнить третью команду данного примера. В третьей команде используется параметр Save для назначения фотографии учетной записи пользователя Ken Myer.
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Чтобы убедиться, что новая фотография назначена учетной записи пользователя, Пользователь Ken Myer может войти в Skype для бизнеса, выбрать "Параметры" и выбрать **"Мой рисунок".** В качестве личного фото пользователя Ken Myer должна отобразиться новая фотография. Администратор может проверить фотографию любого пользователя, введя в адресной строке Internet Explorer URL-адрес, подобный показанному ниже.
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.
  
Обратите внимание, что для того, чтобы сделать фотографию доступной в Skype для бизнеса, не требуется дополнительная настройка. Вместо этого фотография мгновенно станет доступна после ее отправки и запуска `Set-UserPhoto` cmdlet.
