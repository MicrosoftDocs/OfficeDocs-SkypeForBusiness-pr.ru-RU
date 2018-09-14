---
title: Требования к клиентскому Windows и поддержка программного обеспечения
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Сводка: Обзор требований к поддержки клиентов Windows при планировании Скайп Business Server.'
ms.openlocfilehash: fec7996bccddf68fdeb59b8f9e0a185d5c5f18c7
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965636"
---
# <a name="windows-client-requirements-and-software-support"></a>Требования к клиентскому Windows и поддержка программного обеспечения
 
**Сводка:** Обзор требований к поддержке клиентов Windows при планировании Скайп Business Server.
  
В этом разделе содержится сводка программное обеспечение, необходимое для поддержки Скайп для клиентов Windows бизнеса.  Эти клиенты устанавливаются при установке Office 365, а также доступны на [Загрузить Скайп для бизнеса на всех устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Надстройка собраний по сети для Скайп для бизнеса, которая поддерживает Управление собраниями в клиенте системы обмена сообщениями и совместной работы Outlook, автоматическая установка вместе с Скайп для бизнеса. 
  
**Программное обеспечение, необходимое для Скайп для клиента Business и надстройки собраний по сети**

|**Системный компонент**|**Поддерживаемые версии**|
|:-----|:-----|
|Операционная система Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Операционная система Windows 7  <br/> Windows Server 2008 R2 или более поздних версиях с последним пакетом обновления  <br/> **Примечание:** Скайп для бизнеса и надстройка собраний по сети для Скайп для бизнеса не поддерживаются в ОС Windows Vista или Windows XP (любой версии). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Internet Explorer 11 веб-браузер  <br/>  Internet Explorer 10 веб-браузер <br/> Internet Explorer 9 веб-браузер  <br/> Internet Explorer 8 веб-браузер  <br/> Internet Explorer 7 веб-браузер  <br/> Mozilla Firefox  <br/>  Веб-браузера Google Chrome  <br/>**Примечание:** При использовании Скайп для бизнеса с Microsoft Exchange Online и вашей организации развернут проверки подлинности прокси-сервер HTTP, Internet Explorer 8 или более поздней версии является обязательным.           |
|Интеграция с Microsoft Office  <br/> | Outlook 2010 или более поздней версии |
|Интеграция с Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 или более поздней версии  | 
   
## <a name="hardware"></a>Оборудование

Обратитесь к Office 365 [требования к системе](https://products.office.com/en-us/office-system-requirements) для оборудование, необходимое для запуска Скайп для клиента Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Приложение Скайп собраний и Скайп для бизнеса Web App 

Приложение Скайп собраний и Скайп для бизнеса Web App поддерживают определенные сочетания операционных системах и браузерах. Дополнительные сведения см [Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать Скайп для бизнеса функций конференц-связи, не используйте обязательных профилей доменных служб Active Directory для входа в Скайп для клиента Business. Так как обязательных профилей все профили пользователей только для чтения, ключи инфраструктуры открытого ключа (PKI), которые необходимы для Скайп для конференц-связи Business невозможно сохранить в профиль. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Требования к системе для Skype для бизнеса на платформе Windows Phone
 
 
Скайп Майкрософт для бизнеса для Windows Phone предоставляет мгновенного обмена Мгновенными сообщениями, расширенных возможностей присутствия и телефонной связи для пользователей в вашей организации, подключающихся из смартфон или мобильного устройства Windows Professional. Мобильных устройств позволяют пользователям расширения возможностей Скайп для бизнеса. В этом разделе описываются рекомендации по планированию для Скайп для бизнеса для Windows Phone, включая определение необходимых компонентов и технические требования, необходимые компоненты и руководство по развертыванию.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Обязательные требования для работы Skype для бизнеса на платформе Windows Phone

Ниже приведены Скайп наличие необходимых компонентов Business для Windows Phone.
  
- Windows Phone 8.1 или более поздняя версия.
    
- Устройства Windows Phone должны иметь все последние обновления от корпорации Майкрософт. Дополнительные сведения см в разделе 8.1 Windows Phone на [Windows Phone 8 обновления журнала](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- На устройстве должно быть 22 МБ свободного пространства на диске.
    
- В наличии должны иметься активные тарифные планы голосовой связи и передачи данных поставщика услуг.


## <a name="see-also"></a>См. также

[Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md)
  
[Скайп для бизнеса на требования к клиентскому Mac](mac-requirements.md)

[Загрузить Скайп для бизнеса на всех устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Требования к системе для Office 365](https://products.office.com/en-us/office-system-requirements)