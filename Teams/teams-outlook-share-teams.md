---
title: Поделиться с Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Узнайте о функции "Поделиться Teams", которая позволяет пользователям делиться электронной почтой и вложениями из Outlook в любой чат или канал Teams.
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
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="652c8-103">Поделиться с Teams из Outlook</span><span class="sxs-lookup"><span data-stu-id="652c8-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="652c8-104">Отправка Teams из Outlook (Поделиться в Teams) позволяет пользователям обмениваться электронной почтой, включая вложения, от Outlook до любого чата или канала в Teams.</span><span class="sxs-lookup"><span data-stu-id="652c8-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="652c8-105">Outlook надстройки для share to Teams</span><span class="sxs-lookup"><span data-stu-id="652c8-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="652c8-106">Для Teams "Поделиться" требуется надстройка для Outlook.</span><span class="sxs-lookup"><span data-stu-id="652c8-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="652c8-107">Эта надстройка устанавливается автоматически при входе пользователя в веб-приложение Teams или Teams настольного клиента.</span><span class="sxs-lookup"><span data-stu-id="652c8-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="652c8-108">Обязательно просмотрите надстройки для Outlook в [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и Правила клиентского доступа в [Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) чтобы убедиться, что надстройки для Outlook работают правильно.</span><span class="sxs-lookup"><span data-stu-id="652c8-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="652c8-109">Кроме того, отключение подключенных experiences может препятствовать правильной работе надстройок Outlook для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="652c8-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="652c8-110">Дополнительные [сведения см.](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) в Office Подключенные Office.</span><span class="sxs-lookup"><span data-stu-id="652c8-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="652c8-111">Для отправки Teams используется тот же механизм транспорта, что и при отправке сообщений в канал.</span><span class="sxs-lookup"><span data-stu-id="652c8-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="652c8-112">Для общего доступа к чатам сообщения электронной почты (включая вложения) копируется в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="652c8-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="652c8-113">Для общего доступа к каналам сообщения электронной  почты и вложения копируется в папку Сообщения электронной почты в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="652c8-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="652c8-114">Надстройка Outlook для share to Teams использует набор требований 1.7, как описано в документации к надстройки [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), которая содержит сведения о надстройких Outlook, требованиях к среде для надстройок Outlook и конкретных клиентах Outlook, которые поддерживаются с набором требований 1.7.</span><span class="sxs-lookup"><span data-stu-id="652c8-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="652c8-115">Включение и отключение share to Teams</span><span class="sxs-lookup"><span data-stu-id="652c8-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="652c8-116">Надстройка Outlook share to Teams может быть выборочно отключена или включена для каждого пользователя с помощью следующих надстройок PowerShell:</span><span class="sxs-lookup"><span data-stu-id="652c8-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="652c8-117">Отключить надстройку можно только после ее установки.</span><span class="sxs-lookup"><span data-stu-id="652c8-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="652c8-118">Если вы хотите принудительно отключить всех пользователей в клиенте, периодически запускайте сценарий.</span><span class="sxs-lookup"><span data-stu-id="652c8-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="652c8-119">Чтобы отключить надстройку для Outlook share to Teams, запустите [найденный здесь cmdlet](/powershell/module/exchange/disable-app?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="652c8-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="652c8-120">Чтобы включить надстройку для Outlook share to Teams, запустите [найденную здесь надстройку](/powershell/module/exchange/enable-app?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="652c8-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="652c8-121">Браузеры и единый вход</span><span class="sxs-lookup"><span data-stu-id="652c8-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="652c8-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span><span class="sxs-lookup"><span data-stu-id="652c8-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="652c8-123">Подробные сведения о том, какие клиенты [используют конкретные браузеры,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) см. в Office, используемых Office надстройки.</span><span class="sxs-lookup"><span data-stu-id="652c8-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="652c8-124">Для Teams пользователей должны быть включены как сторонние файлы cookie, так и доступ к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="652c8-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="652c8-125">Предоставление Teams с помощью единого входа (SSO), то есть пользователям не нужно предоставлять свои учетные данные при использовании надстройки с помощью share to Teams.</span><span class="sxs-lookup"><span data-stu-id="652c8-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="652c8-126">SSO для Outlook в Интернете по умолчанию поддерживает https://outlook.office365.com/owa/extSSO.aspx URL-адреса и ответы на https://outlook.office.com/owa/extSSO.aspx них.</span><span class="sxs-lookup"><span data-stu-id="652c8-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="652c8-127">Для именных доменов администраторам необходимо добавить соответствующий url-Azure Active Directory ответа.</span><span class="sxs-lookup"><span data-stu-id="652c8-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>