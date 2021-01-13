---
title: Требования к клиенту Windows и поддержка программного обеспечения
ms.author: v-cichur
author: cichur
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
description: Сводка. Просмотрите требования к поддержке клиентов Windows при планировании Skype для бизнеса Server.
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816069"
---
# <a name="windows-client-requirements-and-software-support"></a>Требования к клиенту Windows и поддержка программного обеспечения
 
**Сводка:** Просмотрите требования к поддержке клиентов Windows при планировании Skype для бизнеса Server.
  
В этом разделе приводится итог программного обеспечения, необходимого для поддержки клиентов Windows Skype для бизнеса. Эти клиенты устанавливаются при установке Microsoft 365 или Office 365, а также доступны при загрузке Skype для бизнеса на [всех устройствах.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Надстройка "Собрание по сети" для Skype для бизнеса, которая поддерживает управление собраниями в клиенте outlook для обмена сообщениями и совместной работы, устанавливается автоматически вместе со Skype для бизнеса. 
  
**Программное обеспечение, необходимое для клиента Skype для бизнеса и надстройки "Собрание по сети"**

|**Системный компонент**|**Поддерживаемые версии**|
|:-----|:-----|
|Операционная система Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 или более поздней версии с последним пакетом обновления  <br/> **Примечание.** Skype для бизнеса и надстройка "Собрание по сети" для Skype для бизнеса не поддерживаются в Windows Vista или Windows XP (любой версии). <br/> |
|Установка и обновление  <br/> |Права и разрешения администратора  <br/> |
|Браузер  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet Browser  <br/>  Internet Explorer 10 Браузер <br/> Браузер Internet Explorer 9  <br/> Internet Explorer 8 Браузер  <br/> Internet Explorer 7 Internet Browser  <br/> Веб-браузер Mozilla Firefox  <br/>  Веб-браузер Google Chrome  <br/>**Примечание.** Если вы используете Skype для бизнеса с Microsoft Exchange Online и ваша организация развернула прокси-сервер HTTP для проверки подлинности, Internet Explorer 8 или более поздней.           |
|Интеграция с Microsoft Office  <br/> | Outlook 2010 или более поздней версии; |
|Интеграция с Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 или более поздней  | 
   
## <a name="hardware"></a>Оборудование

Обратитесь к требованиям Microsoft 365 и Office [System](https://products.office.com/office-system-requirements) к оборудованию, необходимому для запуска клиента Skype для бизнеса.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Приложение "Собрания Skype" и Skype для бизнеса Web App 

Приложение "Собрания Skype" и Skype для бизнеса Web App поддерживают определенные сочетания операционных систем и браузеров. Подробные сведения [см. в приложении Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>Использование обязательных профилей

Если вы планируете использовать функции skype для бизнеса conferencing, избегайте использования обязательных профилей доменных служб Active Directory для входов в клиент Skype для бизнеса. Поскольку обязательные профили являются профилями пользователей только для чтения, ключи инфраструктуры открытых ключей (PKI), необходимые для skype для бизнеса conferencing, не могут быть сохранены в профиле. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Системные требования для Skype для бизнеса для Windows Phone
 
 
Microsoft Skype для бизнеса для Windows Phone обеспечивает обмен мгновенными сообщениями, расширенные возможности присутствия и телефонию для пользователей в организации, подключающихся со смартфона или мобильного устройства Windows Professional. Мобильные устройства позволяют пользователям расширить доступ к Skype для бизнеса. В этом разделе описываются рекомендации по планированию Skype для бизнеса для Windows Phone, в том числе определение предварительных и технических требований, обязательных компонентов и рекомендаций по развертыванию.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Предварительные условия для Skype для бизнеса для Windows Phone

Ниже приводится предварительный условия для Skype для бизнеса для Windows Phone.
  
- Windows Phone 8.1 или более поздней версии.
    
- На устройстве с Windows Phone должны быть доступны последние обновления от Корпорации Майкрософт. Подробные сведения см. в разделе Windows Phone 8.1 в истории [обновлений Windows Phone 8.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- На устройстве должно быть 22 МБ доступного дискового пространства.
    
- У пользователя должен быть план голосовой связи и данных от оператора.


## <a name="see-also"></a>См. также

[Планирование клиентов собраний (Веб-приложение и приложение для собраний)](meetings-clients.md)
  
[Требования к клиенту Skype для бизнеса на Mac](mac-requirements.md)

[Скачивание Skype для бизнеса на всех устройствах](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Требования к системе для Microsoft 365 и Office](https://products.office.com/office-system-requirements)
