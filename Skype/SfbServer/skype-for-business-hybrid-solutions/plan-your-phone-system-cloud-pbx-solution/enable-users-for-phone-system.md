---
title: Включение пользователей для телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: В этой статье описано, как включить пользователей для телефонной системы в Office 365 с помощью локальной сети PSTN. Перед выполнением действий, описанных в этом разделе, ознакомьтесь со статьей ниже.
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287463"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="afd89-104">Включение пользователей для телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="afd89-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="afd89-105">В этой статье описано, как включить пользователей для телефонной системы в Office 365 с помощью локальной сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="afd89-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="afd89-106">Перед выполнением действий, описанных в этом разделе, ознакомьтесь со статьей ниже.</span><span class="sxs-lookup"><span data-stu-id="afd89-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="afd89-107">Сведения о настройке гибридного подключения можно найти в статье [планирование гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="afd89-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="afd89-108">Сведения о планировании развертывания можно найти в статье [планирование телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="afd89-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="afd89-109">Дополнительные сведения о телефонной системе в Office 365, в том числе о лицензировании и планах, приведены в статье [планы звонков по PSTN для Skype для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="afd89-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="afd89-110">Перемещение пользователей в телефонную систему в Office 365 с помощью локальной сети PSTN</span><span class="sxs-lookup"><span data-stu-id="afd89-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="afd89-111">Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей в Skype для бизнеса Server или Lync Server 2013 и переместить их в сети.</span><span class="sxs-lookup"><span data-stu-id="afd89-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="afd89-112">Дополнительные сведения можно найти в статье [планирование гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , а также в разделе вопросы и сведения о том, как [включить локальную связь пользователей с корпоративными организациями](enable-the-users-for-enterprise-voice-on-premises.md) (выполняются при подключении пользователей). локально).</span><span class="sxs-lookup"><span data-stu-id="afd89-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="afd89-113">Все пользователи должны быть созданы в службе каталогов Active Directory локально и синхронизированы с Office 365 с помощью поддерживаемой версии Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="afd89-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="afd89-114">Вы не можете включить пользователей для телефонной системы в Office 365, которые были созданы непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="afd89-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="afd89-115">Если вы хотите включить телефонную систему в Office 365 с локальной связью по протоколу КТСОП для пользователя, который был создан в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной службе AD, настроить ее локальную учетную запись, а затем синхронизировать ее с помощью Поддерживаемая версия средства Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="afd89-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="afd89-116">Включение пользователя для телефонной системы в Office 365 со встроенным подключением PSTN и последующим переносом в Skype для бизнеса Online необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="afd89-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="afd89-117">[Включение локальных пользователей для корпоративного голосовой связи](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, когда пользователи размещаются в локальной сети).</span><span class="sxs-lookup"><span data-stu-id="afd89-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="afd89-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (выполняется, пока пользователи размещены в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="afd89-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="afd89-119">[Синхронизация пользователей с облаком и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).</span><span class="sxs-lookup"><span data-stu-id="afd89-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="afd89-120">[Перемещение локальных пользователей в Skype для бизнеса Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (выполняется локально с помощью Windows PowerShell, но с помощью учетных данных администратора Office 365).</span><span class="sxs-lookup"><span data-stu-id="afd89-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="afd89-121">[Предоставление пользователям корпоративной сети голосовой и телефонной системы в Office 365 голосовой почты](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afd89-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

