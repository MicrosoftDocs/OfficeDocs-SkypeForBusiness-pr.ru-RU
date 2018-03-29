---
title: Развертывание инструмента SEFAUtil в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Скайп для Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Развертывание инструмента SEFAUtil в Skype для бизнеса 2015
 
Развертывание средства SEFAUtil в Скайп для Business Server.
  
Для развертывания и управления раскладки вызывать группу, необходимо использовать Скайп Business Server версии средства SEFAUtil. 
  
> [!IMPORTANT]
> На всех компьютерах, на которых планируется запускать инструмент SEFAUtil, должен быть установлен Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK. 
  
Средство SEFAUtil можно запустить в любой пула переднего плана в вашем развертывании.
  
> [!NOTE]
> Статья блога Technet, посвященной более подробных сведений о запуске SEFAUtil, "[способ получения SEFAutil под управлением?](https://go.microsoft.com/fwlink/?LinkId=278940)«. 
  
### <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1. Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Средство SEFAUtil может выполняться только на компьютере, который является частью пула доверенных приложений. При необходимости, определение пула доверенных приложений для пула переднего плана, если вы планируете выполнить SEFAUtil. В командной строке выполните следующую команду:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. Определите инструмент SEFAUtil как доверенное приложение. В командной строке выполните следующую команду:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > При необходимости можно использовать другой порт. 
  
5. Включите топологию с внесенными изменениями. В командной строке выполните следующую команду:
    
  ```
  Enable-CsTopology
  ```

6. Если он еще не установлен, загрузите Скайп Business Server версии средства SEFAUtil из [этого расположения](https://www.microsoft.com/en-us/download/details.aspx?id=52631)и установить его на пул доверенных приложений, созданный на шаге 3.
    
7. Проверьте правильность работы инструмента SEFAUtil следующим образом. 
    
    а. Запустите этот инструмент из командной строки Windows с привилегиями администратора, чтобы отобразить параметры переадресации звонков пользователя в текущем развертывании.
    
    б. Отобразите параметры переадресации звонков пользователя. В командной строке выполните следующую команду:
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

На экране появятся параметры переадресации звонков пользователя.
    

