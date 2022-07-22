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
description: Сведения о функции "Поделиться в Teams", которая позволяет пользователям делиться электронными письмами и вложениями из Outlook в любой чат или канал в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952763"
---
# <a name="share-to-teams-from-outlook"></a>Предоставление общего доступа к Teams из Outlook

Предоставление общего доступа к Teams из Outlook (предоставление общего доступа в Teams) позволяет пользователям делиться электронными письмами, включая вложения, из Outlook в любой чат или канал в Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Надстройка Outlook для совместного использования в Teams 

Для использования функции "Поделиться в Teams" требуется надстройка для Outlook. Эта надстройка устанавливается автоматически при каждом входе пользователя в веб-приложение Teams или настольный клиент Teams.

> [!NOTE]
> Обязательно просмотрите надстройки [для Outlook в Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и правилах клиентского [](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) доступа в Exchange Online, чтобы убедиться, что надстройки для Outlook работают правильно. Кроме того, отключение подключенных функций может помешать правильной работе надстроек Outlook. [Дополнительные сведения см. в разделе "](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)Сетевые функции в Office". Надстройка не поддерживает общие почтовые ящики. 

Совместное использование в Teams использует тот же механизм транспорта, что и при отправке пользователем сообщения по электронной почте каналу. Для общего доступа к чатам сообщения электронной почты (включая вложения электронной почты) копируются в OneDrive отправителя. Для общего доступа к каналам сообщения электронной почты и **вложения** копируются в папку Email сообщений в SharePoint.

Надстройка Outlook для share to Teams использует набор обязательных элементов 1.7, как описано в документации по надстройки [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), которая содержит сведения о надстройки Outlook, требования к среде для надстроек Outlook и конкретные клиенты Outlook, которые поддерживаются с набором обязательных элементов 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Включение или отключение общего доступа в Teams

Надстройку Outlook для общего доступа к Teams можно выборочно отключить или включить для каждого пользователя с помощью следующих командлетов PowerShell.

> [!NOTE]
> Отключение надстройки возможно только после ее установки. Если вы хотите принудительно отключить всех пользователей в клиенте, периодически запускайте сценарий.

Чтобы отключить надстройку для Outlook, используемую share to Teams, выполните [командлет, найденный здесь](/powershell/module/exchange/disable-app).

Чтобы включить надстройку для Outlook, используемую share to Teams, выполните [командлет, найденный здесь](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Браузеры и единый вход

Совместное использование в Teams в Outlook в Интернете классическом клиенте Outlook зависит от браузера WebView. [Дополнительные сведения о](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) том, какие клиенты используют определенные браузеры, см. в браузерах, используемых надстройки Office. 

> [!IMPORTANT]
> Для общего доступа к Teams для браузеров пользователей необходимо включить как сторонние файлы cookie, так и доступ к локальному хранилищу.

Общий доступ к Teams использует единый вход (SSO), что означает, что пользователям не нужно предоставлять свои учетные данные при использовании надстройки через Share to Teams. Единый вход для Outlook в Интернете поддерживает <https://outlook.office365.com/owa/extSSO.aspx> URL-адреса ответа <https://outlook.office.com/owa/extSSO.aspx> и по умолчанию. Для личных доменов администраторам необходимо добавить соответствующий URL-адрес ответа Azure Active Directory.
