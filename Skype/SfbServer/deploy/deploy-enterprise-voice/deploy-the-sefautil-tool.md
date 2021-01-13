---
title: Развертывание средства SEFAUtil в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812389"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Развертывание средства SEFAUtil в Skype для бизнеса
 
Развертывание средства SEFAUtil в Skype для бизнеса Server.
  
Для развертывания группового средства группового вызова и управления им необходимо использовать версию средства SEFAUtil в Skype для бизнеса Server. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool. Скачайте его здесь: [unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Вы также можете скачать SDK UCMA 5, который включает time runtime, здесь: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Средство SEFAUtil можно запустить в любом пуле переднего входа в развертывании. Чтобы запустить средство SEFAUtil, необходимо выполнить шаги 1, 2 и 3 в мастере развертывания Skype для бизнеса на компьютере доверенного приложения. ДЛЯ SEFAUtil требуется локальное хранилище конфигурации, а также сертификат.
  
> [!NOTE]
> Дополнительные сведения о запуске SEFAUtil см. в статье блога["Как запускать SEFAutil?"](https://go.microsoft.com/fwlink/?LinkId=278940) 
  
### <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1. Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Средство SEFAUtil можно запустить только на компьютере, который входит в пул доверенных приложений. При необходимости определите пул доверенных приложений для пула переднего плана, в котором планируется запустить SEFAUtil. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN пула: FQDN сервера или пула, на который будет работать приложение SEFAUtil (обычно это сервер или пул переднего сервера Skype для бизнеса).
    > FQDN регистратора пулов: FQDN сервера переднего сервера или пула Skype для бизнеса, связанного с этим пулом приложений.
    > Сайт пула: ИД сайта, на котором находится этот пул.

4. Определите средство SEFAUtil как доверенного приложения. В командной строке выполните следующую команду:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > При необходимости можно использовать другой порт. 
  
5. В включить топологию с изменениями. В командной строке выполните следующую команду:
    
   ```powershell
   Enable-CsTopology
   ```

6. Если вы еще не сделали этого, скачайте версию средства SEFAUtil в Skype для бизнеса Server из этого расположения и установите ее в пул доверенных приложений, созданный на шаге 3. [](https://www.microsoft.com/download/details.aspx?id=52631)
    
7. Убедитесь, что средство SEFAUtil работает правильно: 
    
    а. Запустите средство в командной панели Windows с привилегиями администратора, чтобы отобразить параметры переадминации вызовов пользователя в развертывании.
    
    б. Отображение параметров переад вызовов пользователя. В командной строке выполните следующую команду:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Отобразить параметры переададантки вызовов для пользователя.
    

