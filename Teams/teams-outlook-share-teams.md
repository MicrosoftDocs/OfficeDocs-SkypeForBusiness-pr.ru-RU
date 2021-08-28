---
title: Поделиться с Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о функции "Поделиться Teams", которая позволяет пользователям делиться электронной почтой и вложениями из Outlook чата или канала в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebbfeecf72be2d042e3686d11be98d3343a3d5f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633983"
---
# <a name="share-to-teams-from-outlook"></a>Поделиться с Teams из Outlook

Отправка Teams из Outlook (Поделиться в Teams) позволяет пользователям обмениваться электронной почтой, включая вложения, от Outlook до любого чата или канала в Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook надстройки для share to Teams 

Для Teams "Поделиться" требуется надстройка для Outlook. Эта надстройка устанавливается автоматически при входе пользователя в веб-приложение Teams или Teams клиенте для настольных пк.

> [!NOTE]
> Обязательно просмотрите надстройки для Outlook в [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и Правила клиентского доступа в [Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) чтобы убедиться, что надстройки для Outlook работают правильно. Кроме того, отключение подключенных опытом может препятствовать правильной работе надстройок Outlook для других пользователей. Дополнительные [сведения см.](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) в Office Подключенные Office.  

Для отправки Teams используется тот же механизм транспорта, что и при отправке сообщений в канал. Для общего доступа к чатам сообщения электронной почты (включая вложения) копируется в OneDrive. Для общего доступа к каналам сообщения электронной  почты и вложения копируется в папку Сообщения электронной почты в SharePoint.

Надстройка Outlook для share to Teams использует набор требований 1.7, как описано в документации надстройок [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)в которой содержатся сведения о надстройки Outlook, требованиях к среде для надстройок Outlook и конкретных клиентах Outlook, которые поддерживаются с набором требований 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Включение и отключение share to Teams

Надстройка Outlook share to Teams может быть выборочно отключена или включена для каждого пользователя с помощью следующих cmdlets PowerShell:

> [!NOTE]
> Отключить надстройку можно только после ее установки. Если вы хотите принудительно отключить всех пользователей в клиенте, периодически запускайте сценарий.

Чтобы отключить надстройку для Outlook share to Teams, запустите [найденный здесь cmdlet](/powershell/module/exchange/disable-app?view=exchange-ps). 

Чтобы включить надстройку для Outlook share to Teams, запустите [найденную здесь надстройку](/powershell/module/exchange/enable-app?view=exchange-ps).

## <a name="browsers-and-single-sign-on"></a>Браузеры и единый вход

Чтобы поделиться Teams, как Outlook в Интернете, так и Outlook классических клиентов, использует браузер WebView. Подробные сведения о том, какие клиенты используют конкретные [браузеры,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) см. в Office, используемых Office надстройки. 

> [!IMPORTANT]
> Для Teams пользователей должны быть включены как сторонние файлы cookie, так и доступ к локальному хранилищу.

Предоставление Teams с помощью единого входа (SSO), то есть пользователям не нужно предоставлять свои учетные данные при использовании надстройки через share to Teams. SSO для Outlook в Интернете по умолчанию поддерживает https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx URL-адреса и отвечать на них. Для именных доменов администраторам необходимо добавить соответствующий url-Azure Active Directory ответа.