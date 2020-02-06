---
title: Требования к клиенту для Windows и поддержка программного обеспечения
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Аннотация: Ознакомьтесь с требованиями поддержки клиента Windows при планировании сервера Skype для бизнеса Server.'
ms.openlocfilehash: a66887b616461a40c6326a66d982a8bfbe8e9605
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803489"
---
# <a name="windows-client-requirements-and-software-support"></a>Требования к клиенту для Windows и поддержка программного обеспечения
 
**Сводка:** При планировании Skype для бизнеса Server ознакомьтесь с требованиями поддержки клиента Windows.
  
В этом разделе приведено краткое описание программного обеспечения, необходимого для поддержки клиентов Skype для бизнеса Windows.  Эти клиенты устанавливаются при установке Office 365, а также доступны на странице [загрузить Skype для бизнеса на всех своих устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Надстройка "собрание по сети" для Skype для бизнеса, поддерживающая управление собраниями в клиенте сообщений Outlook и совместной работы, устанавливается автоматически с помощью Skype для бизнеса. 
  
**Программное обеспечение, необходимое для клиента Skype для бизнеса и надстройки "собрание по сети"**

|**Системный компонент**|**Поддерживаемые версии**|
|:-----|:-----|
|Операционная система Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Операционная система Windows 7  <br/> Windows Server 2008 R2 или более поздняя версия с последним пакетом обновления  <br/> **Примечание.** Надстройка "Skype для бизнеса" и "онлайн-собрание" для Skype для бизнеса не поддерживаются в Windows Vista и Windows XP (любой версии). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Браузер Internet Explorer 11  <br/>  Браузер Internet Explorer 10 <br/> Браузер Internet Explorer 9  <br/> Браузер Internet Explorer 8  <br/> Браузер Internet Explorer 7  <br/> Mozilla Firefox  <br/>  Веб-браузер Google Chrome  <br/>**Примечание.** Если вы используете Skype для бизнеса с Microsoft Exchange Online и ваша организация развернула HTTP-прокси, прошедший проверку подлинности, требуется Internet Explorer 8 или более поздней версии.           |
|Интеграция с Microsoft Office  <br/> | Outlook 2010 или более поздней версии |
|Интеграция с Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 или более поздней версии  | 
   
## <a name="hardware"></a>Оборудование

Ознакомьтесь с [системными требованиями](https://products.office.com/en-us/office-system-requirements) к Office 365 для оборудования, необходимого для работы клиента Skype для бизнеса.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Приложение "собрания Skype" и Skype для бизнеса Web App 

Приложение "собрания Skype" и веб-приложение Skype для бизнеса поддерживают определенные сочетания операционных систем и браузеров. Подробные сведения можно найти в разделе [Планирование клиентов собраний (приложение для веб-приложений и собраний)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать возможности конференции Skype для бизнеса, не используйте обязательные профили доменных служб Active Directory для входа в клиент Skype для бизнеса. Так как обязательные профили являются профилями пользователей только для чтения, ключи инфраструктуры открытых ключей (PKI), необходимые для Конференции Skype для бизнеса, невозможно сохранить в профиле. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Требования к системе для Skype для бизнеса на платформе Windows Phone
 
 
Microsoft Skype для бизнеса для Windows Phone обеспечивает обмен мгновенными сообщениями, расширенные возможности присутствия и телефония для пользователей в вашей организации, которые подключаются с смартфона или мобильного устройства с Windows профессиональный. Мобильные устройства позволяют пользователям расширить возможности Skype для бизнеса. В этой статье описаны вопросы планирования в Skype для бизнеса для Windows Phone, включающий определение требований и технические требования, необходимые компоненты и руководство по развертыванию.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Обязательные требования для работы Skype для бизнеса на платформе Windows Phone

Ниже указаны необходимые условия для Skype для бизнеса для Windows Phone.
  
- Windows Phone 8.1 или более поздняя версия.
    
- На устройстве с Windows Phone должны быть доступны последние обновления от корпорации Майкрософт. Дополнительные сведения можно найти в разделе Windows Phone 8,1 на странице [Журнал обновлений Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- На устройстве должно быть 22 МБ свободного пространства на диске.
    
- В наличии должны иметься активные тарифные планы голосовой связи и передачи данных поставщика услуг.


## <a name="see-also"></a>См. также

[Планирование для клиентов собраний (Skype для бизнеса Web App и приложение "Собрания Skype")](meetings-clients.md)
  
[Клиентские требования Skype для бизнеса для Mac](mac-requirements.md)

[Загрузи Skype для бизнеса на всех устройствах](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Требования к системе для Office 365](https://products.office.com/en-us/office-system-requirements)
