---
title: Планирование современной проверки подлинности (ADAL) с помощью Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: В этой статье объясняется, какая современная проверка подлинности (на основе библиотеки проверки подлинности Active Directory (ADAL) и OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046292"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="da3e2-103">Использование современной проверки подлинности (ADAL) со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da3e2-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="da3e2-104">2016 в этой статье рассматривается современная проверка подлинности (на основе библиотеки проверки подлинности Active Directory (ADAL) и OAuth 2,0), которую можно найти в накопительном пакете обновления для Skype для бизнеса для Skype для бизнеса для Skype для бизнеса Server 2015 или из начального выпуск для Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da3e2-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="da3e2-105">Что такое ADAL?</span><span class="sxs-lookup"><span data-stu-id="da3e2-105">What is ADAL?</span></span>

<span data-ttu-id="da3e2-106">ADAL — это аббревиатура для библиотеки проверки подлинности Active Directory и, кроме OAuth 2,0, это ундерпиннинг современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="da3e2-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="da3e2-107">Эта библиотека кода предназначена для обеспечения доступности защищенных ресурсов в вашем каталоге для клиентских приложений (например, Skype для бизнеса) с помощью маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="da3e2-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="da3e2-108">ADAL работает с OAuth 2,0 для включения дополнительных сценариев проверки подлинности и авторизации, например, многофакторной проверки подлинности (MFA), а также других форм проверки подлинности SAML.</span><span class="sxs-lookup"><span data-stu-id="da3e2-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="da3e2-109">Разнообразные приложения, действующие в качестве клиентов, могут использовать современные проверки подлинности для получения помощи в обеспечении безопасности ресурсов.</span><span class="sxs-lookup"><span data-stu-id="da3e2-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="da3e2-110">В Skype для бизнеса Server эта технология используется между локальными клиентами и локальными серверами, чтобы предоставить пользователям соответствующий уровень авторизации для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="da3e2-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="da3e2-111">Современные диалоги проверки подлинности (которые основаны на ADAL и OAuth 2,0) имеют общие элементы.</span><span class="sxs-lookup"><span data-stu-id="da3e2-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="da3e2-112">Клиент, выполняющий запрос ресурса, в данном случае является клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da3e2-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="da3e2-113">Для клиента необходим определенный уровень доступа, и этот ресурс защищен службой каталогов, в этом случае ресурс является Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="da3e2-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="da3e2-114">Существует подключение OAuth (другими словами), которое предназначено для *авторизации* пользователя на доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="da3e2-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="da3e2-115">(OAuth также известен с использованием более содержательного имени, проверки подлинности "сервер-сервер" и часто сокращается как S2S.)</span><span class="sxs-lookup"><span data-stu-id="da3e2-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="da3e2-116">В беседах Skype для бизнеса Server современная проверка подлинности (ADAL) Skype для бизнеса Server взаимодействуют с ADFS (ADFS 3,0 в Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="da3e2-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="da3e2-117">Проверка подлинности может выполняться с помощью какого-либо другого поставщика удостоверений (IdP), но Skype для бизнеса Server должен быть настроен для обмена данными с ADFS напрямую.</span><span class="sxs-lookup"><span data-stu-id="da3e2-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="da3e2-118">Если вы не настроили ADFS для работы с Skype для бизнеса Server, завершите [установку ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="da3e2-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="da3e2-119">ADAL включено в накопительный пакет обновления 2016 для Skype для бизнеса Server 2015 за Март, а для успешной настройки **необходимо** установить накопительный пакет обновления для Skype для бизнеса за март 2016.</span><span class="sxs-lookup"><span data-stu-id="da3e2-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="da3e2-120">Для Skype для бизнеса Server 2019 он доступен из начального выпуска продукта.</span><span class="sxs-lookup"><span data-stu-id="da3e2-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da3e2-121">В первоначальном выпуске современная проверка подлинности в локальной среде поддерживается только в том случае, если не используется смешанная топология Skype.</span><span class="sxs-lookup"><span data-stu-id="da3e2-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="da3e2-122">Например, если среда является исключительно Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="da3e2-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="da3e2-123">Эта инструкция может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="da3e2-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="da3e2-124">Для успешной настройки необходимо скачать пакет PowerShell, в том числе PS1 и команды, используемые программой ADAL.</span><span class="sxs-lookup"><span data-stu-id="da3e2-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="da3e2-125">Для получения информации о том, как внедрить современные проверки подлинности в Skype для бизнеса, ознакомьтесь со статьей: [использование современной проверки подлинности (ADAL) со Skype для бизнеса](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="da3e2-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
