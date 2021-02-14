---
title: Интеграция с Exchange и SharePoint
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: Сводка. Сведения об интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821109"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Интеграция с Exchange и SharePoint

**Сводка:** Узнайте об интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.

Развертывание Skype для бизнеса Server 2015 можно настроить для интеграции с Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 и SharePoint Server как локально, так и через Интернет. Функции, перечисленные в следующей таблице, поддерживаются для всех клиентов, если не указано иное. Дополнительные сведения о поддержке клиентов см. в таблицах сравнения клиентских функций Skype для бизнеса и [Skype](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) для бизнеса Online на сайте [Clients for Skype for Business Online.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В следующих таблицах перечисляются функции, поддерживаемые в гибридном развертывании при интеграции с Microsoft Exchange Server.

 **Локальное приложение Skype для бизнеса Server и локальное приложение Exchange**


|**Функция**|**Примечания**|
|:-----|:-----|
|Im/Presence в Outlook  <br/> |Дополнительные сведения см. в [сведениях о присутствии и мгновенных мгновенных данных.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Запланировать собрание по сети и присоединиться к нему с помощью Outlook  <br/> |Дополнительные сведения см. в теме ["Интеграция Skype для бизнеса Server 2015 с Exchange Server.](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Мгновенные мгновенные Outlook Web App  <br/> |Дополнительные сведения см. в подстройке "Настройка [гибридной среды" в Skype для бизнеса Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Запланировать собрание по сети и присоединиться к нему с помощью Outlook Web App  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Присоединяйтесь к собраниям по сети в мобильных клиентах  <br/> |Дополнительные сведения см. в [этой теме.](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)  <br/> |
|Публикация состояния на основе сведений о занятости в календаре Outlook  <br/> ||
|Список контактов (через единое хранилище контактов)  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Требуется настольный клиент Lync 2013 или Skype для бизнеса.  <br/>  Дополнительные сведения см. в [настройках Skype для бизнеса Server 2015](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)для использования единого магазина контактов.  <br/> |
|Фотография контакта высокого разрешения в клиенте Lync 2013, клиенте Skype для бизнеса и Lync Web App.  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения см. в настройках использования фотографий высокого разрешения [в Skype для бизнеса Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса для MAC и Mobile необходимо настроить интеграцию Между Skype для бизнеса Server 2015 и Exchange Server, как описано в настройках партнерских приложений [в Skype для](../deploy/integrate-with-exchange-server/configure-partner-applications.md)бизнеса Server и Exchange Server. <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в сети в одном лесу или оба находятся в локальной сети. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик exchange пользователя  <br/> ||
|Архивное содержимое (im и meeting) в Exchange  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения [см. в контрольных списках развертывания для архивации.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Поиск архивного контента  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в сведениях о развертывании локальной системы обмена данными Exchange для предоставления голосовой почты [Lync Server 2013.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)  <br/> |

 **Локальное skype для бизнеса Server и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Im/Presence в Outlook  <br/> |Дополнительные сведения см. в сведениях о настройке интеграции между локальной skype для бизнеса [Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Запланировать собрание по сети и присоединиться к нему с помощью Outlook  <br/> ||
|Мгновенные мгновенные Outlook Web App  <br/> |Дополнительные сведения см. в сведениях о настройке интеграции между локальной skype для бизнеса [Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Запланировать собрание по сети и присоединиться к нему из Outlook Web App  <br/> |Дополнительные сведения см. в сведениях о настройке интеграции между локальной skype для бизнеса [Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Im/Presence в мобильных клиентах  <br/> ||
|Присоединиться к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о занятости в календаре Outlook  <br/> ||
|Список контактов (через единое хранилище контактов).  <br/> |Только Lync Server 2013. Требуется настольный клиент Lync 2013 или Skype для бизнеса.  <br/> Дополнительные сведения см. в [подстроке "Настройка Skype для бизнеса Server 2015 для использования единого магазина контактов"](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Фотография контакта высокого разрешения в клиенте Lync 2013, клиенте Skype для бизнеса и Lync Web App.  <br/> |Дополнительные сведения см. в настройках использования фотографий высокого разрешения [в Skype для бизнеса Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса для MAC и Mobile необходимо настроить интеграцию Между Skype для бизнеса Server 2015 и Exchange Server, как описано в описании настройки интеграции между [локальной](../deploy/integrate-with-exchange-server/outlook-web-app.md)skype для бизнеса Server и Outlook Web App. <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в сети в одном лесу или оба находятся в локальной сети. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик Exchange пользователя  <br/> ||
|Архивное содержимое (im и meeting) в Exchange  <br/> |Дополнительные сведения [см. в контрольных списках развертывания для архивации.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Поиск архивного контента  <br/> |Дополнительные сведения см. в теме ["Настройка Exchange для центра eDiscovery SharePoint"](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в подсети "Предоставление [пользователям Lync Server 2013](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)голосовой почты" в сервере с сервером exchange UM.  <br/> |

 **Skype для бизнеса Online и локальное приложение Exchange**


|**Функция**|**Примечания**|
|:-----|:-----|
|Присутствие в Outlook  <br/> ||
|Ответ с помощью мгновенных сообщений, звонков по STN, звонков Skype или видеозвонков из электронной почты Outlook  <br/> ||
|Планировать собрания по сети и присоединяться к ним через Outlook  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Присоединяйтесь к собраниям по сети в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о занятости в календаре Outlook  <br/> ||
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик exchange пользователя  <br/> ||
|Фотография контакта высокого разрешения в клиенте Lync 2013 или Skype для бизнеса.  <br/> |Требуется Exchange 2016 или Exchange 2013. Это не поддерживается в Lync Web App, когда пользователи находятся в Skype для бизнеса Online.  <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в сети в одном лесу или оба находятся в локальной сети. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик Exchange пользователя  <br/> ||
|История бесед на стороне сервера  <br/> ||

 **Skype для бизнеса Online и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Im/Presence в Outlook  <br/> ||
|Планировать собрания по сети и присоединяться к ним через Outlook  <br/> ||
|Мгновенные мгновенные Outlook Web App  <br/> ||
|Запланировать собрание по сети и присоединиться к нему из Outlook Web App  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Присоединиться к собранию по сети в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о занятости в календаре Outlook  <br/> ||
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик exchange пользователя  <br/> ||
|Список контактов (через единое хранилище контактов)  <br/> |Требуется клиент Lync Server 2013 или Skype для бизнеса  <br/> |
|Фотография контакта высокого разрешения в Lync 2013, клиенте Skype для бизнеса и Lync Web App  <br/> ||
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в сети в одном лесу или оба находятся в локальной сети. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Архивное содержимое (im и meeting) в Exchange  <br/> ||
|Поиск архивного контента  <br/> ||
|Голосовая почта  <br/> ||

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с SharePoint.

||**Локальное развертывание SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Локальное приложение Skype для бизнеса Server 2015** <br/> | Поиск навыков <br/>  Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |
|**Skype для бизнеса Online** <br/> | Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |


