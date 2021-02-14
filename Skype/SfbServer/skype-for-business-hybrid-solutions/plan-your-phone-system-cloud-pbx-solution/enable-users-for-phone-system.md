---
title: Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью через STN. Прежде чем следовать шагам в этом разделе, ознакомьтесь со следующими разделами:'
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359145"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="79879-104">Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79879-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="79879-105">В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью через STN.</span><span class="sxs-lookup"><span data-stu-id="79879-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="79879-106">Прежде чем следовать шагам в этом разделе, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="79879-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="79879-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="79879-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="79879-108">Чтобы узнать о планировании развертывания, см. план телефонной системы с локальной связью по [STN в Skype для бизнеса Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="79879-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="79879-109">Дополнительные информацию о телефонной системе, в том числе о лицензировании и планах, см. в планах звонков по [STN для Skype для бизнеса.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="79879-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="79879-110">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="79879-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="79879-111">Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="79879-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="79879-112">Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="79879-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="79879-113">Перемещение пользователей в телефонную систему с локальной связью через STN</span><span class="sxs-lookup"><span data-stu-id="79879-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="79879-114">Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей локально в Skype для бизнеса Server или Lync Server 2013, а затем переместить их в Интернет.</span><span class="sxs-lookup"><span data-stu-id="79879-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="79879-115">Дополнительные сведения см. в разделе "Планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса [Online",](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) а также в разделе "Enable the users for Корпоративная голосовая связь on premises (performed while the users are homed on-premises)." [](enable-the-users-for-enterprise-voice-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="79879-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="79879-116">Все пользователи должны быть созданы локально в Active Directory и синхронизированы с Microsoft 365 или Office 365 с помощью поддерживаемой версии Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="79879-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="79879-117">Нельзя включить для пользователей телефонной системы в Office 365, созданных непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79879-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="79879-118">Если вы хотите включить телефонную систему с локальной связью через STN для пользователя, созданного в Azure AD, необходимо создать новую учетную запись для этого пользователя в локальной службе AD, настроить учетную запись локально, а затем синхронизировать учетную запись с помощью поддерживаемой версии средства Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="79879-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="79879-119">Для включения для пользователя телефонной системы с локальной связью через STN и их перемещения в Skype для бизнеса Online необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="79879-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="79879-120">[Включить для пользователей локальное Корпоративная голосовая связь](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, когда пользователи находятся в локальной сети).</span><span class="sxs-lookup"><span data-stu-id="79879-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="79879-121">[Назначьте политику маршрутной связи голосовой](assign-a-voice-routing-policy.md) связи (которая выполняется, когда пользователи находятся в локальной сети).</span><span class="sxs-lookup"><span data-stu-id="79879-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="79879-122">[Синхронизация пользователей с облаком](synchronize-users-to-the-cloud-and-assign-licenses.md) и назначение лицензий (выполняется с помощью Office 365).</span><span class="sxs-lookup"><span data-stu-id="79879-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="79879-123">[Перемещение пользователей локальной](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) сети в Skype для бизнеса Online (выполняется с помощью Windows PowerShell локальной службы, но с использованием учетных данных администратора Office 365).</span><span class="sxs-lookup"><span data-stu-id="79879-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="79879-124">[В этом Корпоративная голосовая связь голосовой почты в](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) Интернете и телефонной системе (выполняется с помощью удаленной powerShell).</span><span class="sxs-lookup"><span data-stu-id="79879-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

