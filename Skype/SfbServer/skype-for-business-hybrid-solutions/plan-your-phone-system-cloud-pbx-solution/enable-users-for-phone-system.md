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
description: В этом разделе описывается, как включить для пользователей телефонную систему в Office 365 с локальной связью PSTN. Перед выполнением действий, описанных в этом разделе, необходимо прочесть следующее:.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050191"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="a731a-104">Включение пользователей для телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a731a-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="a731a-105">В этом разделе описывается, как включить для пользователей телефонную систему в Office 365 с локальной связью PSTN.</span><span class="sxs-lookup"><span data-stu-id="a731a-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="a731a-106">Перед выполнением действий, описанных в этом разделе, необходимо прочесть следующее:.</span><span class="sxs-lookup"><span data-stu-id="a731a-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="a731a-107">Чтобы узнать, как настроить гибридное подключение, ознакомьтесь со статьей [планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывание гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a731a-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="a731a-108">Чтобы узнать о планировании развертывания, ознакомьтесь [со статьей Планирование телефонной системы в Office 365 с локальной связью PSTN в Skype для бизнеса Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a731a-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="a731a-109">Дополнительные сведения о телефонной системе в Office 365, в том числе о лицензировании и планах, приведены в статье [планы звонков PSTN для Skype для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="a731a-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="a731a-110">Перемещение пользователей в телефонную систему в Office 365 с использованием локальной сети PSTN</span><span class="sxs-lookup"><span data-stu-id="a731a-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="a731a-111">Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить локальные пользователи в Skype для бизнеса Server или Lync Server 2013, а затем переместить их в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="a731a-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="a731a-112">Для получения дополнительных сведений ознакомьтесь с разделом [планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , а также разделом вопросы, связанными с разделом вопросы и предложения по [включению локальных пользователей](enable-the-users-for-enterprise-voice-on-premises.md) (выполняются, когда пользователи размещены в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="a731a-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="a731a-113">Все пользователи должны быть созданы в локальной службе Active Directory и синхронизированы с Office 365, используя поддерживаемую версию соединителя Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a731a-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="a731a-114">Вы не можете включить пользователей для телефонной системы в Office 365, которые были созданы непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a731a-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="a731a-115">Если вы хотите включить телефонную систему в Office 365 с локальной связью PSTN для пользователя, созданного в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной службе Active Directory, настроить локальную учетную запись, а затем синхронизировать учетную запись с помощью Поддерживаемая версия средства Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="a731a-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="a731a-116">Включение пользователя для телефонной системы в Office 365 с подключением локальной сети PSTN и последующим их переносом в Skype для бизнеса Online необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a731a-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="a731a-117">[Разрешите пользователям локальное подключение к корпоративной голосовой связи](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, пока пользователи размещены в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="a731a-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="a731a-118">[Назначение политики маршрутизации голосовой связи](assign-a-voice-routing-policy.md) (выполняется, когда пользователи размещены в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="a731a-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="a731a-119">[Синхронизация пользователей с облаком и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).</span><span class="sxs-lookup"><span data-stu-id="a731a-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="a731a-120">[Перемещение локальных пользователей в Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (выполняется с помощью Windows PowerShell в локальной среде, но с использованием учетных данных администратора Office 365).</span><span class="sxs-lookup"><span data-stu-id="a731a-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="a731a-121">[Разрешить пользователям доступ к корпоративной голосовой сети и телефонной системе в Office 365 голосовой почты](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a731a-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

