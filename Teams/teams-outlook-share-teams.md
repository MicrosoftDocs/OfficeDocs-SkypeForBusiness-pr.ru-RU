---
title: Предоставление общего доступа Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Сведения о функции "Общий доступ Teams", которая позволяет пользователям делиться электронными письмами и вложениями электронной почты из Outlook в любой чат или канал в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682030"
---
# <a name="share-to-teams-from-outlook"></a>Предоставление общего доступа Teams из Outlook

Предоставление общего доступа Teams из Outlook (общий доступ к Teams) позволяет пользователям делиться электронными письмами, включая вложения, от Outlook до любого чата или канала в Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook надстройки для общего доступа Teams 

Для использования Teams общего доступа требуется надстройка для Outlook. Эта надстройка устанавливается автоматически при каждом входе пользователя в веб-приложение Teams или Teams настольного клиента.

> [!NOTE]
> Обязательно просмотрите надстройки для Outlook в [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и правилах доступа клиентов в [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules), чтобы убедиться, что надстройки для Outlook работают правильно. Кроме того, отключение подключенных функций может помешать правильной Outlook надстроек. [Дополнительные сведения см. в Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) подключенных интерфейсах.  

Совместное использование Teams использует тот же механизм транспорта, что и при отправке пользователем сообщения по электронной почте каналу. Для предоставления общего доступа к чатам сообщения электронной почты (включая вложения электронной почты) копируются в OneDrive. Для общего доступа к каналам сообщения электронной почты и вложения копируются  в папку сообщений электронной почты в SharePoint.

Надстройка Outlook для share to Teams использует набор обязательных элементов 1.7, как описано в документации [по надстройки Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), которая содержит сведения о надстройки Outlook, требования к среде для надстроек Outlook и конкретные клиенты Outlook, поддерживаемые с набором обязательных элементов 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Включение или отключение общего доступа к Teams

Надстройку Outlook share to Teams можно выборочно отключить или включить для каждого пользователя с помощью следующих командлетов PowerShell.

> [!NOTE]
> Отключение надстройки возможно только после ее установки. Если вы хотите принудительно отключить всех пользователей в клиенте, периодически запускайте сценарий.

Чтобы отключить надстройку для Outlook share для Teams, выполните [командлет, найденный здесь](/powershell/module/exchange/disable-app).

Чтобы включить надстройку для Outlook share для Teams, выполните [командлет, найденный здесь](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Браузеры и единый вход

Общий доступ Teams, как в Outlook в Интернете, так и Outlook классических клиентах, зависит от браузера WebView. [Дополнительные сведения о том,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) какие клиенты используют конкретные браузеры, см. в Office браузерах. 

> [!IMPORTANT]
> Общий доступ Teams требует включения сторонних файлов cookie и доступа к локальному хранилищу для браузеров пользователей.

Общий доступ к Teams использует единый вход (SSO), что означает, что пользователям не нужно предоставлять свои учетные данные при использовании надстройки через share для Teams. Единый вход для Outlook в Интернете поддерживает <https://outlook.office365.com/owa/extSSO.aspx> URL-адреса ответа <https://outlook.office.com/owa/extSSO.aspx> и по умолчанию. Для личных доменов администраторам необходимо добавить соответствующий URL-адрес Azure Active Directory ответа.
