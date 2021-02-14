---
title: Планирование современной проверки подлинности (ADAL) в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: В этой статье объясняется, что такое современная проверка подлинности (основанная на библиотеке проверки подлинности Active Directory (ADAL) и OAuth 2.0).
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816229"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="202d1-103">Использование современной проверки подлинности (ADAL) в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="202d1-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="202d1-104">В этой статье вводится современная проверка подлинности (основанная на библиотеке проверки подлинности Active Directory (ADAL) и OAuth 2.0, которую можно найти в накопительном обновлении для Skype для бизнеса server 2015 за март 2016 г. или в первоначальном выпуске Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="202d1-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="202d1-105">Что такое ADAL?</span><span class="sxs-lookup"><span data-stu-id="202d1-105">What is ADAL?</span></span>

<span data-ttu-id="202d1-106">ADAL — это аббревиатура библиотеки проверки подлинности Active Directory, а также OAuth 2.0— основа современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="202d1-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="202d1-107">Эта библиотека кода предназначена для того, чтобы сделать защищенные ресурсы в каталоге доступными для клиентских приложений (например, Skype для бизнеса) с помощью маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="202d1-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="202d1-108">ADAL работает с OAuth 2.0, чтобы включить дополнительные сценарии проверки подлинности и авторизации, например многофакторную проверку подлинности (MFA) и другие формы проверки подлинности SAML.</span><span class="sxs-lookup"><span data-stu-id="202d1-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="202d1-109">Различные приложения, которые выступают в качестве клиентов, могут использовать современную проверку подлинности для получения защищенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="202d1-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="202d1-110">В Skype для бизнеса Server эта технология используется между локальной клиентской и локальной серверами, чтобы предоставить пользователям надлежащий уровень авторизации для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="202d1-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="202d1-111">Беседы современной проверки подлинности (основанные на ADAL и OAuth 2.0) имеют некоторые общие элементы.</span><span class="sxs-lookup"><span data-stu-id="202d1-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="202d1-112">Существует клиент, который запрашивает ресурс, в данном случае это Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="202d1-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="202d1-113">Существует ресурс, к которому клиенту требуется определенный уровень доступа, и этот ресурс защищен службой каталогов, в данном случае это Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="202d1-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="202d1-114">Существует подключение OAuth, другими словами, подключение,  выделенное для авторизации пользователя на доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="202d1-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="202d1-115">(OAuth также известен под более описательным именем , 'Server-to-Server' auth, и часто сокращено как S2S.)</span><span class="sxs-lookup"><span data-stu-id="202d1-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="202d1-116">В беседах skype для бизнеса Server Modern Authentication (ADAL) Skype для бизнеса Server взаимодействует с ADFS (ADFS 3.0 в Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="202d1-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="202d1-117">Проверка подлинности может происходить с помощью другого поставщика удостоверений (IdP), но skype для бизнеса Server необходимо настроить для прямого взаимодействия с ADFS.</span><span class="sxs-lookup"><span data-stu-id="202d1-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="202d1-118">Если вы не настроили ADFS для работы со Skype для бизнеса Server, завершите [установку ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="202d1-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="202d1-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business must be installed and **is** needed for successful configuration.</span><span class="sxs-lookup"><span data-stu-id="202d1-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="202d1-120">Для Skype для бизнеса Server 2019 он доступен в первоначальном выпуске продукта.</span><span class="sxs-lookup"><span data-stu-id="202d1-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="202d1-121">Во время первоначального выпуска современная проверка подлинности в локальной среде поддерживается только в том случае, если не задействована смешанная топология Skype.</span><span class="sxs-lookup"><span data-stu-id="202d1-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="202d1-122">Например, если среда является исключительно Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="202d1-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="202d1-123">Это утверждение может быть под вопросом изменения.</span><span class="sxs-lookup"><span data-stu-id="202d1-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="202d1-124">Для успешной настройки необходимо скачать пакет PowerShell, включая PS1-файлы с командами, используемыми ADAL.</span><span class="sxs-lookup"><span data-stu-id="202d1-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="202d1-125">Сведения о внедрении современной проверки подлинности в Skype для бизнеса см. в теме "Использование современной проверки подлинности [(ADAL)](../../manage/authentication/use-adal.md) в Skype для бизнеса"</span><span class="sxs-lookup"><span data-stu-id="202d1-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
