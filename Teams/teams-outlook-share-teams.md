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
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819481"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="38e41-103">Поделиться в Teams из Outlook</span><span class="sxs-lookup"><span data-stu-id="38e41-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="38e41-104">С помощью Outlook (Share to Teams) пользователи могут обмениваться электронной почтой, включая вложения, из Outlook в любой чат или канал Teams.</span><span class="sxs-lookup"><span data-stu-id="38e41-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="38e41-105">Надстройка Outlook для share to Teams</span><span class="sxs-lookup"><span data-stu-id="38e41-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="38e41-106">Для функции "Поделиться в Teams" требуется надстройка для Outlook.</span><span class="sxs-lookup"><span data-stu-id="38e41-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="38e41-107">Эта надстройка устанавливается автоматически каждый раз, когда пользователь входит в веб-приложение Teams или клиент Teams для настольных пк.</span><span class="sxs-lookup"><span data-stu-id="38e41-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="38e41-108">Обязательно просмотрите правила доступа к надстройки для Outlook в [Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) и правила клиентского доступа в [Exchange Online,](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) чтобы убедиться, что надстройки для Outlook работают правильно.</span><span class="sxs-lookup"><span data-stu-id="38e41-108">Be sure to review [Add-ins for Outlook in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="38e41-109">Кроме того, отключение подключенных опытом может помешать правильной работе надстройки для Outlook.</span><span class="sxs-lookup"><span data-stu-id="38e41-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="38e41-110">Дополнительные [сведения см. в сведениях о подключенных](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) впечатлениях в Office.</span><span class="sxs-lookup"><span data-stu-id="38e41-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="38e41-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span><span class="sxs-lookup"><span data-stu-id="38e41-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="38e41-112">Чтобы поделиться файлом в чате, сообщения электронной почты (включая вложения) копируется в OneDrive отправщика.</span><span class="sxs-lookup"><span data-stu-id="38e41-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="38e41-113">Для общего доступа к каналам сообщения электронной  почты и вложения копируется в папку "Сообщения электронной почты" в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="38e41-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="38e41-114">Надстройка Outlook для Share To Teams использует набор требований 1.7, как описано в документации надстройки [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)который содержит подробные сведения о надстройках Outlook, требованиях среды для надстройок Outlook и конкретных клиентах Outlook, которые поддерживаются с набором требований 1.7.</span><span class="sxs-lookup"><span data-stu-id="38e41-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="38e41-115">Включение и отключение share to Teams</span><span class="sxs-lookup"><span data-stu-id="38e41-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="38e41-116">Надстройка Outlook для share to Teams может быть выборочно отключена или включена для каждого пользователя с помощью следующих командлетов PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38e41-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="38e41-117">Отключить надстройку можно только после ее установки.</span><span class="sxs-lookup"><span data-stu-id="38e41-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="38e41-118">Если вы хотите принудительно отключить отключение для всех пользователей в клиенте, периодически запускайте сценарий.</span><span class="sxs-lookup"><span data-stu-id="38e41-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="38e41-119">Чтобы отключить надстройку для Outlook, используемую share to Teams, запустите [командлет, найденный здесь.](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="38e41-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="38e41-120">Чтобы включить надстройку для Outlook, используемую share to Teams, запустите [командлет, найденный здесь.](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="38e41-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="38e41-121">Браузеры и единый вход</span><span class="sxs-lookup"><span data-stu-id="38e41-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="38e41-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span><span class="sxs-lookup"><span data-stu-id="38e41-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="38e41-123">Подробные [сведения о том,](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) какие клиенты используют конкретные браузеры, см. в браузерах, используемых надстройами Office.</span><span class="sxs-lookup"><span data-stu-id="38e41-123">See [Browsers used by Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="38e41-124">Для совместной работы в Teams необходимо включить сторонние файлы cookie и доступ к локальному хранилищу для браузеров пользователей.</span><span class="sxs-lookup"><span data-stu-id="38e41-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="38e41-125">При совместном использовании в Teams используется единый вход (SSO), то есть пользователям не нужно предоставлять свои учетные данные при использовании надстройки с помощью share to Teams.</span><span class="sxs-lookup"><span data-stu-id="38e41-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="38e41-126">SSO для Outlook в Интернете по умолчанию поддерживает https://outlook.office365.com/owa/extSSO.aspx URL-адреса и отвечает на https://outlook.office.com/owa/extSSO.aspx них.</span><span class="sxs-lookup"><span data-stu-id="38e41-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="38e41-127">Для именных доменов администраторы должны добавить соответствующий URL-адрес ответа Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38e41-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>