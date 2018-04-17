---
title: Desktop client feature comparison for Skype for Business
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Desktop client feature comparison for Skype for Business
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. Вы также сможете сообщить об изменениях пользователям, спланировать процесс развертывания и в полной мере понять преимущества обновления до последней версии клиента.
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. Приобретаемые организацией клиентские или пользовательские лицензии на подписку также влияют на доступность функций для пользователей. Развертывание полного или базового клиента зависит от лицензий или плана, которые приобретет организация. See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>Поддержка расширенных возможностей присутствия
<a name="BKMK_EnhancedPresence"> </a>

В этой таблице рассматриваются расширенные возможности присутствия, выходящие за рамки простых сведений о состоянии присутствия пользователя. 
  
|Компонент или возможность|Клиент Skype для бизнеса 2015 или 2016|Skype для бизнеса на Mac|Lync 2013 client|Магазина Lync Windows|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator для Mac 2011|Lync для Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Публикация состояния  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Просмотр состояния  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Просмотр примечаний к состоянию и сообщений об отсутствии на рабочем месте  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Добавление настраиваемого расположения  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Добавление настраиваемого примечания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Используйте для параметра "Мое фото" фотографию с любого общедоступного сайта  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>Поддержка контактов и групп контактов
<a name="BKMK_Contacts"> </a>

В таблице представлены функции для работы с мгновенными сообщениями и состоянием присутствия ваших контактов. 
  

|Компонент или возможность|Клиент Skype для бизнеса 2015 или 2016|Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Предварительно заполненный список контактов  <br/> |&#x2714;|||||||||
|Просмотр и изменение списка контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Отметка контактов для оповещения об изменении состояния  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Управление уровнем конфиденциальности  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Поиск в корпоративной адресной книге  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Поиск контактов Microsoft Outlook  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Управление группами контактов  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Расширение групп рассылки и групп Office 365  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Поиск групп ответа  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Отображение группы последних контактов  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Отображение группы текущих бесед  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Альтернативные режимы просмотра контактов (например, мозаикой)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|Сортировка по группам  <br/> |&#x2714;|&#x2714;||||
|Сортировка контактов по состоянию (доступности)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Поиск и добавление контактов Exchange  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>Поддержка обмена мгновенными сообщениями
<a name="BKMK_IMSupport"> </a>

В этой таблице рассматриваются функции, связанные с поддержкой обмена мгновенными сообщениями.
  

|Компонент или возможность | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Запуск обмена мгновенными сообщениями или отправка электронного письма контакту  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Переход между текстовыми беседами/отслеживание множества бесед в одном окне с вкладками  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Запись текстовых бесед в Outlook  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Сохранение в Communicator для Mac  <br/> |Сохранение в Lync для Mac  <br/> |
|Использование готовых шаблонов бесед  <br/> |||||&#x2714;|&#x2714;||||
|Проверка орфографии  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Интеграция сохраняемого чата (группового чата)  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Вставка изображений отправителя и получателя в окно мгновенных сообщений  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Отправка рукописных сообщений  <br/> ||||&#x2714;||||||
|Получение рукописных сообщений  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Настройка высокой важности для мгновенных сообщений  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>Поддержка собраний
<a name="BKMK_Conferencing"> </a>

Таблица ниже приводит функции, связанные с поддержкой собраний.
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

При связи между абонентами Skype пользователь Skype для бизнеса Online с планом 1 может принимать участие в сеансах демонстрации рабочего стола и общего доступа к приложениям, если его пригласит пользователь, имеющий доступ к функциям общего доступа.   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|Компонент или возможность | Skype for Business 2016 client | Skype для бизнеса на Mac | Skype для бизнеса Web App | Skype for Business 2015 client | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Добавление звука, воспроизводимого через компьютер  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Добавление видео  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Просмотр видео от нескольких участников (представление галереи)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Видеодемонстрация экрана  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|Специальные элементы управления для выступающих на собрании  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Доступ к подробному списку участников собрания  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Обмен мгновенными сообщениями между множеством пользователей  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Демонстрация рабочего стола (если эта возможность включена)  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Общий доступ к программе (если эта возможность включена)  <br/> |&#x2714;|Только просмотр  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||Только просмотр  <br/> |
|Добавление анонимных участников (если эта возможность включена)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Аудиоконференции с телефонным подключением  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Организация собрания с функцией "Начать собрание"  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Добавление и демонстрация файлов Microsoft PowerPoint  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|Только презентация  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|Переход по файлам Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Добавление и изменение заметок к собранию в OneNote  <br/> |&#x2714;||Только изменение (без добавления)  <br/> |&#x2714;|&#x2714;|||||||
|Использование доски  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Проведение опросов  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Отправка файлов для совместного использования  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Планирование собрания или конференции  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|Отключение видео участников  <br/> |&#x2714;||&#x2714;|||||||||
|Отключение мгновенных сообщений на собрании  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Отключение микрофонов аудитории  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Функция "Сделать всех участниками"  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Трансляция собраний Skype  <br/> |&#x2714;|||||||||||
|Делегат может запланировать собрание от имени делегирующего  <br/> |&#x2714;|Только Skype для бизнеса Online <br/>|&#x2714;|||||||||
|Синхронизация делегатов между Skype для бизнеса и Outlook  <br/> |&#x2714;||&#x2714;|||||||||
|Видеодемонстрация экрана  <br/> |&#x2714;| Только Skype для бизнеса Online <br/> |&#x2714;||&#x2714;|||||||
|Фиксация видео в центре внимания  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Передача управления демонстрацией экрана  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. Эта функция не поддерживается в Skype для бизнеса Web App в Max OSX.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Поддержка голосовой связи (телефонии)
<a name="BKMK_Telephony"> </a>

В этой таблице приводятся функции, связанные с поддержкой служб голосовой связи.
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | Компонент или возможность | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Выполнение звонка  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Звонок контакту щелчком мыши  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Передача вызова  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Управление переадресацией звонков  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Управление параметрами групповых звонков  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Управление делегатами  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Звонок в группу ответа  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Поддержка экстренных служб (Е-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to SIP URI(s) for E-911 call  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to distribution list for E-911 call  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Подключение к голосовой почте, настройка или изменение приветствия  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Уведомление о пропущенных звонках  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Звонки от имени другого контакта (сценарий с управляющим и делегатом)  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Прием делегатом звонков другого пользователя  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Работа с большим количеством звонков  <br/> |||||&#x2714;|&#x2714;||||
|Парковка вызовов  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|Ответ на групповой звонок  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Маршрутизация на основе расположения  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Управление группами ответа и групповых звонков  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>Поддержка внешних пользователей
<a name="BKMK_ExternalUsers"> </a>

В этой таблице рассматриваются функции, связанные с поддержкой внутренних пользователей, размещенных в сети ТСОП.
  

|Компонент или возможность | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Инициация текстовой беседы с общедоступным контактом  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Начало сеанса обмена мгновенными сообщениями с федеративным контактом  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Выполнение двусторонних или многопользовательских звонков внешним пользователям  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>Поддержка записи
<a name="BKMK_Recording"> </a>

В этой таблице рассматриваются функции, связанные с поддержкой записи собраний.
  
| Future/capability** | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Запись звука, видео, общий доступ к приложениям, совместный доступ к рабочему столу и отправка контента на стороне клиента  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Запись передаваемых файлов, общих страниц OneNote и примечаний PowerPoint на стороне клиента  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Выбор предпочитаемого разрешения для записи  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. Для записи требуются полные права клиента Skype для бизнеса.
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>Современная проверка подлинности
<a name="BKMK_Recording"> </a>

В следующей таблице приводятся функции, требующие поддержки современной проверки подлинности. 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Компонент или возможность | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator для Mac 2011 | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Современная проверка подлинности  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Многофакторная проверка подлинности  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Проверка подлинности на основе сертификатов  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>Поддержка архивации, соблюдения требований и ведения журналов
<a name="BKMK_Archiving"> </a>

В этой таблице рассматриваются функции, связанные с поддержкой архивации и ведения журналов.
  

 | Компонент или возможность | Клиент Skype для бизнеса 2015 или 2016 | Skype для бизнеса на Mac | Lync 2013 client | Магазина Lync Windows | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator для Mac 2011** | Lync для Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Архивация текстовых бесед в журнале бесед Outlook  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Сохранение в Communicator для Mac  <br/> |Сохранение в Lync для Mac  <br/> |
|Архивация звука, видео, общий доступ к приложениям, совместный доступ к рабочему столу и отправка контента на стороне клиента  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Архивация передачи файлов, общих страниц OneNote и заметок PowerPoint на стороне клиента  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>Ограничения клиентов 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Ограничения базовых клиентов
<a name="Full-Basic"> </a>

Приведенные ниже функции доступны при использовании полного клиента и недоступны при использовании базового клиента.  
  
- Управление параметрами групповых звонков
    
- Управление делегатами
    
- Звонки от имени другого контакта (сценарий с руководителем и делегатом)
    
- Обработка звонков другого пользователя делегатом
    
- Управление большим количеством звонков
    
- Выполнение звонка в группу ответа
    
- Парковка вызовов
    
- Change greeting
    
- Ответ на групповой вызов
    
### <a name="online-or-hybrid-user-account-limitations"></a>Ограничения интерактивных или гибридных учетных записей пользователей
<a name="Online-Hybrid"> </a>

Учетные записи пользователей могут существовать в интерактивной или локальной среде, при этом доступные функции будут различаться. Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- Расширенные возможности присутствия. Используйте для параметра "Мое фото" фотографию с любого общедоступного сайта.
    
- Контакты. Поиск групп ответа.
    
- Поддержка обмена мгновенными сообщениями. Интеграция сохраняемого чата (группового чата).
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- Внешние пользователи. Выполнение двусторонних или многопользовательских звонков внешним пользователям.
    
## <a name="see-also"></a>Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

