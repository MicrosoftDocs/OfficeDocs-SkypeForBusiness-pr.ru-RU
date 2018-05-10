---
title: Развертывание инструмента SEFAUtil в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Скайп для Business Server.
ms.openlocfilehash: 4def73d0bca655569275f61d9ebfeafb4ab7e3d4
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Развертывание инструмента SEFAUtil в Skype для бизнеса 2015
 
Развертывание средства SEFAUtil в Скайп для Business Server.
  
Для развертывания и управления раскладки вызывать группу, необходимо использовать Скайп Business Server версии средства SEFAUtil. 
  
> [!IMPORTANT]
> Среда выполнения Microsoft Unified Communications Managed API (UCMA) 5 необходимо установить на любом компьютере, где предполагается запустить средство SEFAUtil. Загружаемый файл расположен здесь: [Объединенных коммуникаций управляемых API 5.0 времени выполнения](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Также можно загрузить пакет SDK 5 UCMA, которая включает в себя среды выполнения, здесь: [Пакет SDK для UCMA 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Средство SEFAUtil можно запустить в любой пула переднего плана в вашем развертывании. Для запуска средства SEFAUtil выполните шаги 1, 2 и 3 из Скайп для бизнеса мастер развертывания на компьютере доверенных приложений. SEFAUtil требует локального хранилища конфигурации должен быть установлен, а также сертификат.
  
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
    

