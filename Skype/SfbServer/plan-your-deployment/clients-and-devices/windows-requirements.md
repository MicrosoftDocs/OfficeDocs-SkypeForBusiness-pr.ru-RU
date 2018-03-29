---
title: Требования к клиентскому Windows и поддержка программного обеспечения
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Сводка: Обзор требований к поддержки клиентов Windows при планировании Скайп Business Server 2015.'
ms.openlocfilehash: 1a9af80b55073240a53843c9fee912c0c521ba73
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Требования к клиентскому Windows и поддержка программного обеспечения
 
**Сводка:** Просмотрите требования для поддержки клиентов Windows при планировании Скайп Business Server 2015.
  
В этом разделе содержится сводка программное обеспечение, необходимое для поддержки Скайп для бизнеса 2015 2016 клиентов и Windows.
  
Эти клиенты устанавливаются при установке Office 365, а также доступны на [Загрузить Скайп для бизнеса на всех устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Надстройка собраний по сети для Скайп для бизнеса, которая поддерживает Управление собраниями в клиенте системы обмена сообщениями и совместной работы Outlook, автоматическая установка вместе с Скайп для бизнеса. 
  
**Программное обеспечение, необходимое для Скайп для бизнеса и собрания по сети надстройки для Скайп для бизнеса**


|**Компонент системы**|**Поддерживаемые версии**|
|:-----|:-----|
|Операционная система Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Операционная система Windows 7  <br/> Windows Server 2008 R2 с последним пакетом обновления  <br/> **Примечание:** Скайп для бизнеса и надстройка собраний по сети для Скайп для бизнеса не поддерживаются в ОС Windows Vista или Windows XP (любой версии). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Internet Explorer 11 веб-браузер  <br/>  Internet Explorer 10 веб-браузер <br/> Internet Explorer 9 веб-браузер  <br/> Internet Explorer 8 веб-браузер  <br/> Internet Explorer 7 веб-браузер  <br/> Mozilla Firefox  <br/> **Примечание:** При использовании Скайп для бизнеса с Microsoft Exchange Online и вашей организации развернут проверки подлинности прокси-сервер HTTP, Internet Explorer 8 или более поздней версии является обязательным.           |
|Интеграция с Microsoft Office  <br/> |Для полного набора возможностей интеграции:  <br/> • Outlook 2016 клиент обмена сообщениями и совместной работы  <br/> • Outlook 2013 клиент обмена сообщениями и совместной работы  <br/> • Outlook 2010 клиент обмена сообщениями и совместной работы  <br/> |
|Интеграция с Microsoft Exchange  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Оборудование

Обратитесь к Office 365 [требования к системе](https://products.office.com/en-us/office-system-requirements) для оборудование, необходимое для запуска Скайп для клиента Business.
  
## <a name="skype-for-business-web-app-browsers"></a>Скайп Business веб-браузеров, приложения

Скайп для бизнеса Web App поддерживает определенные сочетания операционной системы и браузера. Дополнительные сведения см [Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Поддержка Microsoft Office

Скайп для клиентов, Business Server 2015 поддерживает интеграцию с различными версиями Microsoft Office.
  
- Скайп для функций интеграции бизнеса поддерживаются в Outlook 2016, Outlook 2013 и Outlook 2010.
    
- Скайп для функций интеграции бизнеса поддерживаются в Microsoft Exchange Server 2016, Microsoft Exchange Server 2013 и Microsoft Exchange Server 2010.
    
- Надстройка собраний по сети для Скайп для бизнеса поддерживается Office 2016, Office 2013 и Microsoft Office 2010.
    
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать Скайп для бизнеса функций конференц-связи, не используйте обязательных профилей доменных служб Active Directory для входа в Скайп для клиента Business. Так как обязательных профилей все профили пользователей только для чтения, ключи инфраструктуры открытого ключа (PKI), которые необходимы для Скайп для конференц-связи Business невозможно сохранить в профиль. 
  
## <a name="macintosh-operating-systems"></a>Операционные системы Macintosh

Скайп для бизнеса на требования для поддержки Mac подробно рассмотрены в [Скайп для бизнеса на требования к клиентскому Mac](mac-requirements.md).
  
## <a name="see-also"></a>См. также

#### 

[Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md)
  
[Скайп для бизнеса на требования к клиентскому Mac](mac-requirements.md)
#### 

[Загрузить Скайп для бизнеса на всех устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Требования к системе для Office 365](https://products.office.com/en-us/office-system-requirements)

