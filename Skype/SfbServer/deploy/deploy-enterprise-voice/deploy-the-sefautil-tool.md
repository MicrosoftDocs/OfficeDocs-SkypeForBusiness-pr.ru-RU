---
title: Развертывание средства SEFAUtil в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Skype для бизнеса Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986814"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Развертывание средства SEFAUtil в Skype для бизнеса
 
Развертывание средства SEFAUtil в Skype для бизнеса Server.
  
Для развертывания и управления групповой отправке звонков необходимо использовать версию средства SEFAUtil для Skype для бизнеса Server. 
  
> [!IMPORTANT]
> Среда выполнения Microsoft Unified Communications Managed API (UCMA) 5 должна быть установлена на любой компьютер, на котором планируется запускать средство SEFAUtil. Скачайте его здесь: [Managed Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Кроме того, вы можете скачать пакет SDK UCMA 5, включающий среду выполнения, здесь: [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Средство SEFAUtil можно использовать в любом пуле переднего плана в развертывании. Для запуска средства SEFAUtil необходимо выполнить действия 1, 2 и 3 в мастере развертывания Skype для бизнеса на доверенном компьютере приложения. Для SEFAUtil требуется, чтобы локальное хранилище конфигурации присутствовало, а также для сертификата.
  
> [!NOTE]
> Дополнительные сведения о запуске SEFAUtil можно найти в статье блог "[как получить SEFAUtil?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1. Выполните вход на компьютер, на котором установлена командная консоль Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе **Делегирование разрешений на установку**.
    
2. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.
    
3. Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений. При необходимости определите доверенный пул приложений для пула переднего плана, где планируется запускать SEFAUtil. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Полное доменное имя пула: полное доменное имя сервера или пула, на котором будет размещаться приложение SEFAUtil (обычно это интерфейсный сервер или пул Skype для бизнеса).
    > Полное доменное имя регистратора пула: полное доменное имя сервера или пула приложений Skype для бизнеса, связанных с этим пулом приложений.
    > Сайт пула: идентификатор сайта, на котором размещен этот пул.

4. Определите средство SEFAUtil в качестве доверенного приложения. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > При необходимости можно использовать другой порт. 
  
5. Включите топологию с изменениями. В командной строке выполните следующую команду:
    
   ```powershell
   Enable-CsTopology
   ```

6. Если вы еще не сделали это, Скачайте версию средства SEFAUtil в Skype для бизнеса Server из [этого расположения](https://www.microsoft.com/download/details.aspx?id=52631)и установите ее в пул доверенных приложений, созданный на шаге 3.
    
7. Убедитесь, что средство SEFAUtil работает правильно, как показано ниже. 
    
    а. Запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.
    
    б. Отображение параметров переадресации звонков пользователя. В командной строке выполните следующую команду:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Будут отображены параметры переадресации звонков для пользователя.
    

