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
description: Сводка. Сведения о интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.
ms.openlocfilehash: 01ebbdd94098fa9f7785f41fedbcbdfe7589f03e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092837"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Интеграция с Exchange и SharePoint

**Сводка:** Узнайте об интеграции Skype для бизнеса Server 2015 с Exchange и SharePoint.

Вы можете настроить развертывания Skype для бизнеса Server 2015 для интеграции с Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 и SharePoint Server, как локально, так и онлайн. Функции, перечисленные в следующей таблице, поддерживаются всеми клиентами, если не указано иное. Дополнительные сведения о поддержке клиентов см. в таблице сравнения клиентских функций [настольных](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) компьютеров для skype для бизнеса и таблицы сравнения клиентов Skype для бизнеса в Интернете для [клиентов Skype для бизнеса Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В следующих таблицах представлены функции, поддерживаемые в гибридном развертывании при интеграции с Microsoft Exchange Server.

 **Skype для бизнеса Server в помещениях и Exchange в помещениях**


|**Функция**|**Примечания**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> |Дополнительные сведения см. в [чате и присутствии.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|Расписание и участие в онлайн-собрании через Outlook  <br/> |Дополнительные сведения см. в [ссылке Интеграция Skype для бизнеса Server 2015 с Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|IM/Presence in Outlook Web App  <br/> |Дополнительные сведения см. в [руб. Настройка гибридной среды в Skype для бизнеса Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Запланировать и присоединиться к собранию через Outlook Web App  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Регистрация онлайн-собраний в мобильных клиентах  <br/> |Дополнительные сведения см. в [дополнительных сведениях о развертывании мобильности.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|Публикация состояния на основе сведений о свободном/загруженном календаре Outlook  <br/> ||
|Список контактов (через Единый магазин контактов)  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Требуется клиент настольного компьютера Lync 2013 или Skype для бизнеса.  <br/>  Дополнительные сведения см. в [дополнительных сведениях: Настройка Skype для бизнеса Server 2015 для использования единого магазина контактов.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Контактная фотография с высоким разрешением в клиенте Lync 2013, клиенте Skype для бизнеса и веб-приложении Lync.  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения см. в дополнительных сведениях о настройке использования фотографий с высоким разрешением в [Skype для бизнеса Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса для MAC и Mobile необходимо настроить интеграцию между Skype для бизнеса Server 2015 и Exchange Server, как описано в [настройках](../deploy/integrate-with-exchange-server/configure-partner-applications.md)партнерских приложений в Skype для бизнеса Server и Exchange Server . <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя  <br/> ||
|Архивавка контента (im и meeting) в Exchange  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения см. в [списке развертывания для архивации.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|Поиск архивного контента  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в сообщении о развертывании локальной системы обмена данными Exchange для обеспечения голосовой почты [Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)  <br/> |

 **Skype для бизнеса Server в помещениях и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> |Дополнительные сведения см. в [веб-сайте Configure integration between on-premises Skype for Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Расписание и участие в онлайн-собрании через Outlook  <br/> ||
|IM/Presence in Outlook Web App  <br/> |Дополнительные сведения см. в [веб-сайте Configure integration between on-premises Skype for Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Запланировать и присоединиться к онлайн-собранию из Outlook Web App  <br/> |Дополнительные сведения см. в [веб-сайте Configure integration between on-premises Skype for Business Server 2015 и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Чат/присутствие в мобильных клиентах  <br/> ||
|Присоединяйтесь к онлайн-собранию в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о свободном/загруженном календаре Outlook  <br/> ||
|Список контактов (через Единый магазин контактов).  <br/> |Только Lync Server 2013. Требуется клиент настольного компьютера Lync 2013 или Skype для бизнеса.  <br/> Дополнительные сведения см. в [дополнительных сведениях: Настройка Skype для бизнеса Server 2015 для использования единого магазина контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Контактная фотография с высоким разрешением в клиенте Lync 2013, клиенте Skype для бизнеса и веб-приложении Lync.  <br/> |Дополнительные сведения см. в дополнительных сведениях о настройке использования фотографий с высоким разрешением в [Skype для бизнеса Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса для MAC и Mobile необходимо настроить интеграцию между Skype для бизнеса Server 2015 и Exchange Server, как описано в настройках интеграции между локальной skype для бизнеса [Server и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|История пропущенных бесед и журналы вызовов пишутся в почтовый ящик Exchange пользователя  <br/> ||
|Архивавка контента (im и meeting) в Exchange  <br/> |Дополнительные сведения см. в [списке развертывания для архивации.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|Поиск архивного контента  <br/> |Дополнительные сведения см. в [центре настройки exchange для sharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в сообщении о предоставлении голосовой почты [пользователей Lync Server 2013 в Хозяйской электронной почте Exchange.](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)  <br/> |

 **Skype для бизнеса в Интернете и Exchange в помещениях**


|**Функция**|**Примечания**|
|:-----|:-----|
|Присутствие в Outlook  <br/> ||
|Отвечать с помощью чата, вызова PSTN, skype call или видеосвязи из электронной почты Outlook  <br/> ||
|Расписание и участие в онлайн-собраниях через Outlook  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Регистрация онлайн-собраний в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о свободном/загруженном календаре Outlook  <br/> ||
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя  <br/> ||
|Контактная фотография с высоким разрешением в Lync 2013 или клиент Skype для бизнеса.  <br/> |Требуется Exchange 2016 или Exchange 2013. Это не поддерживается в веб-приложении Lync, когда пользователи находятся в Skype для бизнеса Online.  <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|История пропущенных бесед и журналы вызовов пишутся в почтовый ящик Exchange пользователя  <br/> ||
|История разговоров стороной сервера  <br/> ||

 **Skype для бизнеса в Интернете и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> ||
|Расписание и участие в онлайн-собраниях через Outlook  <br/> ||
|IM/Presence in Outlook Web App  <br/> ||
|Запланировать и присоединиться к онлайн-собранию из Outlook Web App  <br/> ||
|Чат/присутствие в мобильных клиентах  <br/> ||
|Присоединяйтесь к онлайн-собранию в мобильных клиентах  <br/> ||
|Публикация состояния на основе сведений о свободном/загруженном календаре Outlook  <br/> ||
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя  <br/> ||
|Список контактов (через Единый магазин контактов)  <br/> |Требуется клиент Lync Server 2013 или Skype для бизнеса  <br/> |
|Контактная фотография с высоким разрешением в Lync 2013, клиент Skype для бизнеса и веб-приложение Lync  <br/> ||
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. в [гибридных решениях Skype для бизнеса.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Архивавка контента (im и meeting) в Exchange  <br/> ||
|Поиск архивного контента  <br/> ||
|Голосовая почта  <br/> ||

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с SharePoint.

||**Локальное развертывание SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Локальное приложение Skype для бизнеса Server 2015** <br/> | Поиск навыков <br/>  Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |
|**Skype для бизнеса Online** <br/> | Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |