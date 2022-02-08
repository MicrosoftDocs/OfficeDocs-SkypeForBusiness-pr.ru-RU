---
title: Windows клиентских требований и поддержки программного обеспечения
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: Сводка. Просмотрите требования Windows поддержки клиентов при планировании Skype для бизнеса Server.
ms.openlocfilehash: 50b0583e55c872e15e59c8510503b5b11ffc8714
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395011"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows клиентских требований и поддержки программного обеспечения
 
**Сводка:** Просмотрите Windows клиентской поддержки при планировании Skype для бизнеса Server.
  
В этом разделе подводятся итоги программного обеспечения, необходимого для поддержки Skype для бизнеса Windows клиентов. Эти клиенты устанавливаются при Microsoft 365 или Office 365 установки, а также доступны на Skype для бизнеса всех [устройствах](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Надстройка online meeting for Skype для бизнеса, которая поддерживает управление собраниями из Outlook обмена сообщениями и совместной работы, устанавливается автоматически с Skype для бизнеса. 
  
**Программное обеспечение, необходимое для Skype для бизнеса клиента и надстройки для собраний в Интернете**

|**Системный компонент**|**Поддерживаемые версии**|
|:-----|:-----|
|Windows операционной системы  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows 2008 R2 или более поздней версии с последним пакетом служб  <br/> **Примечание:** Skype для бизнеса и надстройка для Skype для бизнеса собраний не поддерживаются на Windows Vista или Windows XP (любой версии). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Браузер Internet Explorer 11  <br/>  Internet Explorer 10 браузера <br/> Интернет-браузер Internet Explorer 9  <br/> Internet Explorer 8 браузера  <br/> Интернет-браузер Internet Explorer 7  <br/> Веб-браузер Mozilla Firefox  <br/>  Веб-браузер Google Chrome  <br/>**Примечание:** Если вы используете Skype для бизнеса с Microsoft Exchange Online и ваша организация развернула прокси-сервер HTTP для проверки подлинности, Internet Explorer 8 или позже.           |
|Интеграция с Microsoft Office  <br/> | Outlook 2010 или более поздней версии; |
|Интеграция с Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 или более поздней  | 
   
## <a name="hardware"></a>Оборудование

Обратитесь к Microsoft 365 и Office [систем](https://products.office.com/office-system-requirements) для оборудования, необходимого для запуска Skype для бизнеса клиента.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype и Skype для бизнеса Web App 

Приложение Skype meetings и Skype для бизнеса Web App поддерживает определенные сочетания операционных систем и браузеров. Подробные сведения см. [в материале Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать Skype для бизнеса, не используйте обязательные профили служб домена Active Directory для регистрации Skype для бизнеса клиента. Так как обязательные профили — это только для чтения профили пользователей, ключи инфраструктуры открытых ключей (PKI), необходимые для Skype для бизнеса для конференциалов, не могут быть сохранены в профиле. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Требования к системе для Skype для бизнеса на Windows Phone
 
 
Microsoft Skype для бизнеса на Windows Phone обеспечивает обмен мгновенными сообщениями (IM), расширенное присутствие и телефонию для пользователей в вашей организации, которые подключаются со смартфона или Windows Professional мобильного устройства. Мобильные устройства позволяют пользователям расширять доступ к Skype для бизнеса. В этом разделе описываются соображения планирования для Skype для бизнеса на Windows Phone, которые включают определение предварительных условий и технических требований, обязательных компонентов и руководства по развертыванию.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype для бизнеса на Windows Phone предпосылки

Ниже приводится Skype для бизнеса на Windows Phone условия.
  
- Windows Phone 8.1 или более поздней.
    
- Устройство Windows Phone должно иметь последние обновления, доступные в Корпорации Майкрософт. Подробные сведения см. в разделе Windows Phone 8.1 в [Windows Phone обновления 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Устройство должно иметь 22 МБ доступного дискового пространства.
    
- У пользователя должен быть голос и план данных от перевозчика.


## <a name="see-also"></a>См. также

[Планирование для клиентов собраний (Web App и Meetings App)](meetings-clients.md)
  
[Skype для бизнеса требования к клиентам Mac](mac-requirements.md)

[Загрузка Skype для бизнеса всех устройств](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 и Office системных требований](https://products.office.com/office-system-requirements)
