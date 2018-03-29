---
title: Включение пользователей для телефонной системой в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: В этом разделе описываются предоставлению пользователям разрешения для телефонной системой в Office 365 с помощью локального подключения к ТСОП. Прежде чем выполнять действия, описанные в этом разделе, прочитайте следующие:.
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="c4fe9-104">Включение пользователей для телефонной системой в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c4fe9-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="c4fe9-105">В этом разделе описываются предоставлению пользователям разрешения для телефонной системой в Office 365 с помощью локального подключения к ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="c4fe9-106">Прежде чем выполнять действия, описанные в этом разделе, прочитайте следующие:.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="c4fe9-107">Узнайте, как настроить гибридного подключения, приведены в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывания гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="c4fe9-108">Дополнительные сведения о планировании развертывания, содержатся [Планирование телефонной системы в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="c4fe9-109">Чтобы узнать больше о телефонной системой в Office 365, включая лицензирования и планы, видеть [вызов ТСОП планов для Скайп для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="c4fe9-110">Переход на телефонной системой в Office 365 с помощью локального подключения к ТСОП</span><span class="sxs-lookup"><span data-stu-id="c4fe9-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="c4fe9-111">Перед перемещением пользователей на Скайп для бизнеса в Интернет, рекомендуется включить пользователей локально в Скайп для Business Server или Lync Server 2013 и переместите их в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="c4fe9-112">Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и в разделе необходимо учитывать для [предоставления пользователям корпоративной голосовой связи на локальном](enable-the-users-for-enterprise-voice-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="c4fe9-113">Все пользователи должен быть создан в Active Directory при локальном и синхронизируются с Office 365 с помощью поддерживаемая версия соединителя Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="c4fe9-114">Пользователи не могут включить для телефонной системой в Office 365, которые были созданы непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="c4fe9-115">Если вы хотите включить телефонной системой в Office 365 с помощью подключения к ТСОП локального пользователя, который был создан в Azure AD, необходимо создать новую учетную запись для этого пользователя в своей локальной AD, настройте учетную запись локальной и затем синхронизировать с помощью учетной записи поддерживаемая версия соединительной Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c4fe9-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="c4fe9-116">Включение пользователю телефонной системой в Office 365 с помощью подключения к ТСОП в локальной и перемещая их в Скайп для бизнеса Online необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c4fe9-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="c4fe9-117">[Включение пользователей для корпоративной голосовой связи локально](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется в то время как пользователи, размещенные локально).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="c4fe9-118">[Назначение маршрутизации политики голосовой связи](assign-a-voice-routing-policy.md) (выполняется в то время как пользователи, размещенные локально).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="c4fe9-119">[Синхронизация пользователей в облаке и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="c4fe9-120">[Переместите пользователей в локальной Скайп для бизнеса в Интернет](move-on-premises-users-to-skype-for-business-online.md) (выполняется с помощью Windows PowerShell в локальной, но с помощью учетных данных администратора Office 365).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="c4fe9-121">[Включить пользователей для корпоративной голосовой связи через Интернет и телефонной системой в голосовой почты Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell).</span><span class="sxs-lookup"><span data-stu-id="c4fe9-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

