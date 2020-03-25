---
title: Требования к клиентам Windows и поддержка программного обеспечения
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
description: 'Сводка: при планировании Skype для бизнеса Server ознакомьтесь с требованиями поддержки клиентов Windows.'
ms.openlocfilehash: 39f9efcd2008dacb653538b56f2aff3fcb8b7887
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928242"
---
# <a name="windows-client-requirements-and-software-support"></a>Требования к клиентам Windows и поддержка программного обеспечения
 
**Сводка:** При планировании Skype для бизнеса Server ознакомьтесь с требованиями поддержки клиентов Windows.
  
В этом разделе описывается программное обеспечение, необходимое для поддержки клиентов Skype для бизнеса Windows.  Эти клиенты устанавливаются при установке Office 365, а также доступны на странице [Загрузка Skype для бизнеса на всех устройствах](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Надстройка "собрание по сети" для Skype для бизнеса, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, устанавливается автоматически вместе со Skype для бизнеса. 
  
**Программное обеспечение, необходимое для клиента Skype для бизнеса и надстройки "собрание по сети"**

|**Системный компонент**|**Поддерживаемые версии**|
|:-----|:-----|
|Операционная система Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 или более поздняя версия с последним пакетом обновления  <br/> **Примечание:** Skype для бизнеса и надстройка "собрание по сети" для Skype для бизнеса не поддерживаются в Windows Vista или Windows XP (любая версия). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Браузер Internet Explorer 11  <br/>  Браузер Internet Explorer 10 <br/> Браузер Internet Explorer 9  <br/> Браузер Internet Explorer 8  <br/> Браузер Internet Explorer 7  <br/> Веб-браузер Mozilla Firefox  <br/>  Веб-браузер Google Chrome  <br/>**Примечание:** Если вы используете Skype для бизнеса с Microsoft Exchange Online, а ваша организация развернула прокси-сервер HTTP, прошедший проверку подлинности, требуется Internet Explorer 8 или более поздней версии.           |
|Интеграция с Microsoft Office  <br/> | Outlook 2010 или более поздней версии; |
|Интеграция с Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 или более поздней версии  | 
   
## <a name="hardware"></a>Оборудование

Ознакомьтесь с [требованиями к системе](https://products.office.com/office-system-requirements) Office 365 для оборудования, необходимого для запуска клиента Skype для бизнеса.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Приложение для собраний Skype и веб-приложение Skype для бизнеса 

Приложение для собраний Skype и веб-приложение Skype для бизнеса поддерживают определенные сочетания операционных систем и браузеров. Дополнительные сведения см. в статье [Plan for meetings for meetings (приложение для веб-приложений и собраний)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать функции конференц-связи Skype для бизнеса, не используйте обязательные профили доменных служб Active Directory, чтобы войти в клиент Skype для бизнеса. Так как обязательные профили являются профилями пользователей с доступом только для чтения, ключи инфраструктуры открытых ключей (PKI), необходимые для конференц-связи Skype для бизнеса, невозможно сохранить в профиле. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Требования к системе для Skype для бизнеса для Windows Phone
 
 
Microsoft Skype для бизнеса для Windows Phone обеспечивает обмен мгновенными сообщениями, расширенные сведения о присутствии и телефонию для пользователей в вашей организации, которые подключаются к смартфону или мобильному устройству Windows профессиональный. Мобильные устройства позволяют пользователям расширить возможности Skype для бизнеса. В этом разделе приведены рекомендации по планированию Skype для бизнеса для Windows Phone, которые включают определение необходимых условий и технических требований, обязательные компоненты и руководство по развертыванию.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Предварительные требования для Skype для бизнеса для Windows Phone

Ниже приведены необходимые условия для Skype для бизнеса для Windows Phone.
  
- Windows Phone 8,1 или более поздней версии.
    
- На устройстве с Windows Phone должны быть доступны последние обновления от корпорации Майкрософт. Дополнительные сведения можно найти в разделе Windows Phone 8,1 в [журнале обновлений Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- На устройстве должно быть 22 МБ свободного места на диске.
    
- Пользователь должен иметь план голосовой связи и данных от оператора.


## <a name="see-also"></a>См. также

[Планирование для клиентов собраний (приложение для веб-приложений и собраний)](meetings-clients.md)
  
[Требования к клиентам в Skype для бизнеса и Mac](mac-requirements.md)

[Скачайте Skype для бизнеса на всех устройствах](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Требования к системе для Office 365](https://products.office.com/office-system-requirements)
