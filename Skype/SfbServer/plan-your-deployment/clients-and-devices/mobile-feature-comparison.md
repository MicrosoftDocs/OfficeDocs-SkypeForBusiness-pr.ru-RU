---
title: Mobile client feature comparison for Skype for Business
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
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Mobile client feature comparison for Skype for Business
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- вход, push-уведомления и общие функциональные возможности;
    
- расширенные сведения о присутствии;
    
- контакты и группы контактов;
    
- обмен мгновенными сообщениями;
    
- Skype for Business to Skype for Business audio and video
    
- конференц-связь
    
- телефония;
    
- внешние пользователи;
    
- архивирование и соответствие требованиям.
    
-  Современная проверка подлинности
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>вход, push-уведомления и общие функциональные возможности;

 
 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Поддержка push-уведомлений  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|Сведения учетных записей для нескольких пользователей можно кэшировать на одном устройстве  <br/> |&#x2714;||||
|Программа чтения с экрана/голос за кадром  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|Использование внешней клавиатуры для поддержки специальных возможностей  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Поддержка программы улучшения качества программного обеспечения Майкрософт   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>Поддержка расширенного уведомления о присутствии


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Публикация и просмотр состояния  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр состояния в соответствии со сведениями о доступности в календаре  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр примечаний к состоянию и сообщений об отсутствии на рабочем месте  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Добавление настраиваемого расположения  <br/> |&#x2714;||||
|Добавление настраиваемого примечания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Публикация состояния в соответствии со сведениями о доступности в календаре   <br/> |&#x2714; &#x2776; ||||
|Настройка состояния присутствия вручную (например, "Занят", "Не беспокоить" и т. д.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>Поддержка контактов и групп контактов


 | Функция или возможность  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Просмотр списка контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр групп контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр группы "Часто используемые контакты"  <br/> |&#x2714;||||
|Изменение списка контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Отметка контактов для оповещения об изменении состояния  <br/> |&#x2714;||||
|Управление уровнем конфиденциальности  <br/> |&#x2714;||||
|Поиск в корпоративной адресной книге  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Поиск по списку контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Управление группами контактов  <br/> |&#x2714;|||&#x2714;|
|Расширение списков рассылки  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Поиск групп ответа  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Отображение или скрытие фотографий контактов  <br/> |&#x2714;|&#x2714;|||
|Прикрепление контакта на начальный экран  <br/> ||&#x2714;|||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>Поддержка обмена мгновенными сообщениями


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Инициирование обмена мгновенными сообщениями с контактом  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Обмен мгновенными сообщениями между множеством пользователей  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Приглашение других участников из окна беседы  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Отображение текущих бесед  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Переход по нескольким текстовым беседам  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Автоматическая запись текстовых бесед в Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Отправка текстовой беседы в виде сообщения электронной почты  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Отправка сообщения электронной почты контакту  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр пропущенных приглашений к участию в беседе  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Вибрационный сигнал о входящих мгновенных сообщениях  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | Компонент или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Для передачи видеоизображения на мобильное устройство по умолчанию необходимо подключение Wi-Fi.  
  
## <a name="conferencing-support"></a>Поддержка конференц-связи 


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ссылка в напоминании о собрании, позволяющая присоединиться к видеособранию или собранию через VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Обмен мгновенными сообщениями между множеством пользователей  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Использование конференц-связи с обратным звонком (сервер звонит на мобильное устройство)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Использование аудиоконференций с телефонным подключением  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр видео с собрания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр видео от нескольких участников (представление галереи)  <br/> |&#x2714;||||
|Ожидание в зале ожидания собрания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Специальные элементы управления для выступающих на собрании  <br/> |&#x2714;||||
|Доступ к подробному списку участников собрания для аудиоконференций  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Доступ к подробному списку участников собрания для конференций с обменом мгновенными сообщениями  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Общий доступ к рабочему столу или программе  <br/> |&#x2714;||||
|View shared desktop or program (VbSS or RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Просмотр общих файлов PowerPoint  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Добавление и презентация файлов PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Использование средств собрания (использование доски, проведение опросов, общий доступ к файлам)  <br/> |&#x2714;||||
|Навигация по списку собраний  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр дополнительных сведения об участниках собрания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Запуск незапланированной групповой беседы с несколькими участниками непосредственно с клиента или устройства   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>Поддержка телефонной связи 


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Передача вызова  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Консультативный перевод  <br/> |&#x2714; &#x2778; ||||
|Управление переадресацией звонков  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Управление параметрами групповых звонков  <br/> |&#x2714; &#x2776; ||||
|Управление делегатами  <br/> |&#x2714; &#x2776; ||||
|Звонок в группу ответа  <br/> |&#x2714; &#x2776; ||||
|Поддержка экстренных служб  <br/> |&#x2714; &#x2777; ||||
|Звонки от имени другого контакта (сценарий с управляющим и делегатом)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Использование вызовов с рабочего телефона   <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Доступ к голосовой почте  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>Доступ внешних пользователей


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Инициация текстовой беседы с общедоступным контактом  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Начало сеанса обмена мгновенными сообщениями с федеративным контактом  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Выполнение двусторонних звонков внешним пользователям  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Выполнение многопользовательских звонков внешним пользователям  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. Для звонка на мобильный телефон федеративного контакта посредством звонка на его опубликованный рабочий номер этот федеративный контакт обязан вручную назначить вам уровень конфиденциальности "Коллеги".
  
## <a name="address-book-integration"></a>Взаимодействие с адресной книгой


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Звонки контактам из адресной книги устройства  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Поддержка архивации и обеспечения соответствия требованиям


 | Функция или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Архивация на стороне клиента  <br/> |&#x2714;||||
|Запись на стороне клиента  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>Современная проверка подлинности

В следующей таблице приводятся функции, требующие поддержки современной проверки подлинности.
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Компонент или возможность  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Современная проверка подлинности  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Многофакторная проверка подлинности  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Проверка подлинности на основе сертификатов  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

