---
title: Предоставление общего доступа в Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о функции "Общий доступ к Teams", которая позволяет пользователям обмениваться электронной почтой и вложениями из Outlook в любом чате или канале в Teams.
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198491"
---
# <a name="share-to-teams-from-outlook"></a>Предоставление общего доступа в Teams из Outlook

Общий доступ к Teams из Outlook (Общий доступ к Teams) позволяет пользователям обмениваться электронной почтой, включая вложения, из Outlook в любой чат или канал в Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Надстройка Outlook для предоставления общего доступа в Teams 

Для функции "Общий доступ к Teams" требуется надстройка для Outlook. Эта надстройка устанавливается автоматически, когда пользователь входит в веб-приложение Teams или классический клиент Teams.

> [!NOTE]
> Обязательно ознакомьтесь с [разделом Надстройки для Outlook в Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и [Правила клиентского доступа в Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules), чтобы убедиться, что надстройки для Outlook работают правильно. Кроме того, отключение подключенных интерфейсов может помешать правильной работе надстроек для Outlook. Дополнительные сведения см. [в статье Подключенные возможности в Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) . Общие почтовые ящики не поддерживаются надстройкой. 

Общий доступ к Teams использует тот же механизм транспорта, что и при отправке пользователем электронной почты каналу. Для предоставления общего доступа к чатам сообщения электронной почты (включая вложения) копируются в OneDrive отправителя. Для общего доступа к каналам сообщения электронной почты и вложения копируются в папку **Email сообщений** в SharePoint.

Надстройка Outlook для предоставления общего доступа к Teams использует набор требований 1.7, как описано в [документации по надстройкам Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), которая включает сведения о надстройках Outlook, требованиях к среде для надстроек Outlook и конкретных клиентах Outlook, поддерживаемых с набором требований 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Включение или отключение общего доступа к Teams

Надстройку Outlook для предоставления общего доступа к Teams можно выборочно отключить или включить для каждого пользователя с помощью следующих командлетов PowerShell.

> [!NOTE]
> Отключить надстройку можно только после установки надстройки. Если вы хотите принудительно отключить для всех пользователей в клиенте, периодически запускайте скрипт.

Чтобы отключить надстройку для Outlook, используемую командлетом Share to Teams, выполните [командлет, приведенный здесь](/powershell/module/exchange/disable-app).

Чтобы включить надстройку для Outlook, используемую командлетом Share to Teams, выполните [командлет, приведенный здесь](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Браузеры и единый вход

Предоставление общего доступа в Teams в классических клиентах Outlook в Интернете и Outlook использует браузер WebView. Дополнительные сведения о том, какие клиенты используют определенные браузеры, см. [в статье Браузеры, используемые надстройками Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) . 

> [!IMPORTANT]
> Для предоставления общего доступа к Teams необходимо включить сторонние файлы cookie и доступ к локальному хранилищу для браузеров пользователей.

Общий доступ к Teams использует единый вход ( SSO), что означает, что пользователям не нужно указывать свои учетные данные при использовании надстройки через Общий доступ к Teams. Единый вход для Outlook в Интернете по умолчанию поддерживает <https://outlook.office365.com/owa/extSSO.aspx> URL-адреса ответов и <https://outlook.office.com/owa/extSSO.aspx> ответов. Для доменов vanity администраторы должны добавить соответствующий URL-адрес ответа Azure Active Directory.
