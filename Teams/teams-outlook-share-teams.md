---
title: Поделиться в Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Узнайте о функции "Поделиться в Teams", которая позволяет пользователям отправлять сообщения электронной почты и вложения из Outlook в любой чат или канал Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098225"
---
# <a name="share-to-teams-from-outlook"></a>Поделиться в Teams из Outlook

С помощью Outlook (Share to Teams) пользователи могут обмениваться электронной почтой, включая вложения, из Outlook в любой чат или канал Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Надстройка Outlook для share to Teams 

Для функции "Поделиться в Teams" требуется надстройка для Outlook. Эта надстройка устанавливается автоматически каждый раз, когда пользователь входит в веб-приложение Teams или клиент Teams для настольных ПК.

> [!NOTE]
> Обязательно просмотрите правила доступа к надстройки для Outlook в [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и правила клиентского доступа в [Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) чтобы убедиться, что надстройки для Outlook работают правильно. Кроме того, отключение подключенных опытом может помешать правильной работе надстройки для Outlook. Дополнительные [сведения см. в сведениях о подключенных](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) впечатлениях в Office.  

Для отправки в Teams используется тот же механизм транспорта, что и при отправке сообщений в канал. Чтобы поделиться файлом в чате, сообщения электронной почты (включая вложения) копируется в OneDrive отправщика. Для общего доступа к каналам сообщения электронной  почты и вложения копируется в папку "Сообщения электронной почты" в SharePoint.

Надстройка Outlook для Share To Teams использует набор требований 1.7, как описано в документации надстройки [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)который содержит подробные сведения о надстройках Outlook, требованиях к среде для надстройок Outlook и конкретных клиентах Outlook, которые поддерживаются с набором требований 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Включение и отключение share to Teams

Надстройка Outlook для share to Teams может быть выборочно отключена или включена для каждого пользователя с помощью следующих командлетов PowerShell:

> [!NOTE]
> Отключить надстройку можно только после ее установки. Если вы хотите принудительно отключить отключение для всех пользователей в клиенте, периодически запускайте сценарий.

Чтобы отключить надстройку для Outlook, используемую share to Teams, запустите [командлет, найденный здесь.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Чтобы включить надстройку для Outlook, используемую share to Teams, запустите [командлет, найденный здесь.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Браузеры и единый вход

Совместное приложение Teams в классических и веб-клиентах Outlook использует браузер WebView. Подробные [сведения о том,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) какие клиенты используют конкретные браузеры, см. в браузерах, используемых надстройами Office. 

> [!IMPORTANT]
> Для совместной работы в Teams необходимо включить сторонние файлы cookie и доступ к локальному хранилищу для браузеров пользователей.

При совместном использовании в Teams используется единый вход (SSO), то есть пользователям не нужно предоставлять свои учетные данные при использовании надстройки с помощью share to Teams. SSO для Outlook в Интернете по умолчанию поддерживает https://outlook.office365.com/owa/extSSO.aspx URL-адреса и отвечает на https://outlook.office.com/owa/extSSO.aspx них. Для именных доменов администраторы должны добавить соответствующий URL-адрес ответа Azure Active Directory.