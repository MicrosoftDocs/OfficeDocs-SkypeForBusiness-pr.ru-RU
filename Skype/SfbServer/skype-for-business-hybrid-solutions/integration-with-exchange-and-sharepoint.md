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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: Сводка. Сведения об интеграции Skype для бизнеса Server 2015 г. с Exchange и SharePoint.
ms.openlocfilehash: a2caf4cf409f3631ebc0a85cd2957b30e9d36d2a
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013143"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Интеграция с Exchange и SharePoint

**Сводка:** Узнайте о Skype для бизнеса Server 2015 г. с Exchange и SharePoint.

Можно настроить развертывание Skype для бизнеса Server 2015 г. для интеграции с Microsoft Exchange Server 2016 г., Microsoft Exchange Server 2013 г., Microsoft Exchange Server 2010 г. и SharePoint Server, как на локальном, так и на сайте. Функции, перечисленные в следующей таблице, поддерживаются всеми клиентами, если не указано иное. Дополнительные сведения о поддержке [](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) клиентов см. в Skype для бизнеса и Skype для бизнеса онлайн-таблицы сравнения клиентов в Клиенты для [Skype для бизнеса Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В следующих таблицах представлены функции, поддерживаемые в гибридном развертывании при интеграции с Microsoft Exchange Server.

 **Skype для бизнеса Server помещений и Exchange помещениях**


|**Функция**|**Примечания**|
|:-----|:-----|
|Im/Presence in Outlook  <br/> |Дополнительные сведения см. в [чате и присутствии.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|Запланировать и присоединиться к собранию через Outlook  <br/> |Дополнительные сведения см. в [Skype для бизнеса Server 2015 Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Im/Presence в Outlook Web App  <br/> |Дополнительные сведения см. в [рубке Настройка гибридной среды в Skype для бизнеса Server 2015 г.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Запланировать и присоединиться к собранию через Outlook Web App  <br/> ||
|Im/Presence в мобильных клиентах  <br/> ||
|Регистрация онлайн-собраний в мобильных клиентах  <br/> |Дополнительные сведения см. в [дополнительных сведениях о развертывании мобильности.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|Публикация состояния на основе Outlook и сведений о занятости в календаре  <br/> ||
|Список контактов (через Единый магазин контактов)  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Требуется клиент Lync 2013 или Skype для бизнеса настольного компьютера.  <br/>  Дополнительные сведения см. в [Skype для бизнеса Server 2015 г.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)для использования единого магазина контактов.  <br/> |
|Контактная фотография с высоким разрешением в клиенте Lync 2013, Skype для бизнеса клиенте и Lync Web App.  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения см. в дополнительных сведениях о настройке использования фотографий с высоким разрешением [в Skype для бизнеса Server 2015 г.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса mac и Mobile необходимо настроить интеграцию между Skype для бизнеса Server 2015 и Exchange Server, как описано в [настройках](../deploy/integrate-with-exchange-server/configure-partner-applications.md)партнерских приложений в Skype для бизнеса Server и Exchange Server . <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. в [перенастройке гибридного подключения между](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md)Skype для бизнеса Server и Teams. <br/> |
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя  <br/> ||
|Архивавка контента (im и meeting) в Exchange  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> Дополнительные сведения см. в [списке развертывания для архивации.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|Поиск архивного контента  <br/> |Требуется Exchange 2016 или Exchange 2013.  <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в Exchange развертывания локальной системы электронной почты для обеспечения голосовой почты [Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)  <br/> |

 **Skype для бизнеса Server на месте и Exchange Online**


|**Функция**|**Примечания**|
|:-----|:-----|
|Im/Presence in Outlook  <br/> |Дополнительные сведения см. в перенастройке интеграции между локальной Skype для бизнеса Server [2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) и Outlook Web App <br/> |
|Запланировать и присоединиться к собранию через Outlook  <br/> ||
|Im/Presence в Outlook Web App  <br/> |Дополнительные сведения см. в перенастройке интеграции между локальной Skype для бизнеса Server [2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) и Outlook Web App <br/> |
|Запланировать и присоединиться к онлайн-собранию из Outlook Web App  <br/> |Дополнительные сведения см. в перенастройке интеграции между локальной Skype для бизнеса Server [2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) и Outlook Web App <br/> |
|Чат/присутствие в мобильных клиентах  <br/> ||
|Присоединяйтесь к онлайн-собранию в мобильных клиентах  <br/> ||
|Публикация состояния на основе Outlook и сведений о занятости в календаре  <br/> ||
|Список контактов (через Единый магазин контактов).  <br/> |Только Lync Server 2013. Требуется клиент Lync 2013 или Skype для бизнеса настольного компьютера.  <br/> Дополнительные сведения см. в [Skype для бизнеса Server 2015 г. для использования единого магазина контактов](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Контактная фотография с высоким разрешением в клиенте Lync 2013, Skype для бизнеса клиенте и Lync Web App.  <br/> |Дополнительные сведения см. в дополнительных сведениях о настройке использования фотографий с высоким разрешением [в Skype для бизнеса Server 2015 г.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Для фотографий в приложении Skype для бизнеса mac и Mobile интеграция между Skype для бизнеса Server 2015 и Exchange Server должна быть настроена так, как описано в настройках интеграции между локальной Skype для бизнеса Server [и Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Делегирования собраний  <br/> |Поддерживается только в том случае, если оба пользователя находятся в интернете в одном лесу или оба находятся в локальном помещении. Дополнительные сведения см. [в Skype для бизнеса гибридных решений.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|История пропущенных бесед и журналы вызовов пишутся в почтовый ящик Exchange пользователя  <br/> ||
|Архивавка контента (im и meeting) в Exchange  <br/> |Дополнительные сведения см. в [списке развертывания для архивации.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|Поиск архивного контента  <br/> |Дополнительные сведения см. в Exchange центре SharePoint [eDiscovery](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Голосовая почта  <br/> |Дополнительные сведения см. в веб-сайте Предоставление голосовой почты пользователей [Lync Server 2013 в размещенный Exchange um](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um).  <br/> |


## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с SharePoint.

||**Локальное развертывание SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype для бизнеса Server 2015** <br/> | Поиск навыков <br/>  Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |
|**Skype для бизнеса Online** <br/> | Присутствие в SharePoint <br/> | Присутствие в SharePoint <br/> |
