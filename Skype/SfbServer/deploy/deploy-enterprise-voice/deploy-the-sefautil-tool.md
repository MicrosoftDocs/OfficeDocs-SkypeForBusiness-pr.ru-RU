---
title: Развертывание средства SEFAUtil в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Skype для бизнеса Server.
ms.openlocfilehash: 40f35f227a2e1753f3362cd01b29883e06e1b893
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761537"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Развертывание средства SEFAUtil в Skype для бизнеса
 
Развертывание средства SEFAUtil в Skype для бизнеса Server.
  
Чтобы развернуть и управлять групповым вызовом, необходимо использовать Skype для бизнеса Server версию средства SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime должен быть установлен на любом компьютере, на котором планируется запустить средство SEFAUtil. Скачайте его здесь: [Управляемый API единой связи 5.0 Время запуска](https://www.microsoft.com/download/details.aspx?id=47344). Вы также можете скачать SDK UCMA 5, который включает время запуска, здесь: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Вы можете запустить средство SEFAUtil в любом пуле переднего конца в развертывании. Чтобы запустить средство SEFAUtil, необходимо выполнить этапы 1, 2 и 3 из мастера развертывания Skype для бизнеса на надежном компьютере приложения. ДЛЯ SEFAUtil требуется локальное хранилище конфигурации, а также сертификат.
  
> [!NOTE]
> Дополнительные сведения о запуске SEFAUtil см. в статье в блоге " Как получить[запуск SEFAutil?](/archive/blogs/jenstr/how-to-get-sefautil-running)". 
  
### <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1. Войдите на компьютер, на котором Skype для бизнеса Server в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Средство SEFAUtil можно запускать только на компьютере, который является частью доверенного пула приложений. При необходимости определите доверенный пул приложений для пула переднего плана, в котором планируется запустить SEFAUtil. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN пула: FQDN сервера или пула, который будет принимать приложение SEFAUtil (обычно Skype для бизнеса сервер или пул).
    > FQDN регистратора пула: FQDN сервера Skype для бизнеса или пула, связанных с этим пулом приложений.
    > Сайт пула. ID сайта, на котором находится этот пул.

4. Определите средство SEFAUtil как надежное приложение. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > При необходимости можно использовать другой порт. 
  
5. Включить топологию с помощью изменений. В командной строке выполните следующую команду:
    
   ```powershell
   Enable-CsTopology
   ```

6. Если вы еще не сделали этого, загрузите Skype для бизнеса Server версию средства SEFAUtil из этого расположения [и](https://www.microsoft.com/download/details.aspx?id=52631)установите его в доверенный пул приложений, созданный на шаге 3.
    
7. Убедитесь, что средство SEFAUtil работает правильно, следующим образом: 
    
    А. Запустите средство из командной Windows с привилегиями администратора, чтобы отобразить параметры переададации вызовов пользователя в развертывании.
    
    Б. Отображение параметров переададки вызовов пользователя. В командной строке выполните следующую команду:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Будут отображаться параметры переададки вызовов для пользователя.
