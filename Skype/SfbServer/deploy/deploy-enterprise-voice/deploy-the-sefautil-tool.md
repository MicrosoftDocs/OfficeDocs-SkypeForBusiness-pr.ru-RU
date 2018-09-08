---
title: Развертывание средства SEFAUtil в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Скайп для Business Server.
ms.openlocfilehash: dfb2b1e4634332fcf88fdce7b09a02f925dd120e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884802"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Развертывание средства SEFAUtil в Скайп для бизнеса
 
Развертывание средства SEFAUtil в Скайп для Business Server.
  
Для развертывания и управления раскладки вызывать группу, необходимо использовать Скайп Business Server версии средства SEFAUtil. 
  
> [!IMPORTANT]
> Среда выполнения Microsoft Unified Communications Managed API (UCMA) 5 необходимо установить на любом компьютере, где предполагается запустить средство SEFAUtil. Загружаемый файл расположен здесь: [Объединенных коммуникаций управляемых API 5.0 времени выполнения](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Также можно загрузить пакет SDK 5 UCMA, которая включает в себя среды выполнения, здесь: [Пакет SDK для UCMA 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Средство SEFAUtil можно запустить в любой пула переднего плана в вашем развертывании. Для запуска средства SEFAUtil выполните шаги 1, 2 и 3 из Скайп для бизнеса мастер развертывания на компьютере доверенных приложений. SEFAUtil требует локального хранилища конфигурации должен быть установлен, а также сертификат.
  
> [!NOTE]
> Дополнительные сведения о запуске SEFAUtil, посвященной статья блога "[способ получения SEFAutil под управлением?](https://go.microsoft.com/fwlink/?LinkId=278940)«. 
  
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
    

