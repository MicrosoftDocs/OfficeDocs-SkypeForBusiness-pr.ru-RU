---
title: Включить для пользователей доступ к Корпоративная голосовая связь локально
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Чтобы пользователь может использовать телефонную систему (облачную УАБ), необходимо сначала включить для Корпоративная голосовая связь и назначить ему номер телефона. Это можно сделать с помощью локального развертывания, когда пользователь по-прежнему находится в локальном развертывании.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359195"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="fe773-104">Включить для пользователей доступ Корпоративная голосовая связь локально</span><span class="sxs-lookup"><span data-stu-id="fe773-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="fe773-105">Чтобы пользователь может использовать телефонную систему (облачную УАБ), необходимо сначала включить для Корпоративная голосовая связь и назначить ему номер телефона.</span><span class="sxs-lookup"><span data-stu-id="fe773-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="fe773-106">Это можно сделать с помощью локального развертывания, когда пользователь по-прежнему находится в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="fe773-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="fe773-107">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="fe773-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="fe773-108">Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="fe773-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="fe773-109">Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="fe773-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="fe773-110">Чтобы включить для пользователя Корпоративная голосовая связь локально и назначить номер телефона</span><span class="sxs-lookup"><span data-stu-id="fe773-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="fe773-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fe773-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fe773-112">Используйте меню "Пуск" или ярлык рабочего стола, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fe773-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="fe773-113">Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fe773-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fe773-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fe773-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="fe773-115">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="fe773-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="fe773-116">В таблице щелкните учетную запись пользователя Skype для бизнеса Online, которую вы хотите включить для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="fe773-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="fe773-117">В меню **"Правка"** щелкните **"Показать сведения".**</span><span class="sxs-lookup"><span data-stu-id="fe773-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="fe773-118">В **области телефонии** щелкните **Корпоративная голосовая связь.**</span><span class="sxs-lookup"><span data-stu-id="fe773-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="fe773-119">Щелкните **URI** линии и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="fe773-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="fe773-120">Затем нажмите **кнопку "Зафиксировать".**</span><span class="sxs-lookup"><span data-stu-id="fe773-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="fe773-121">Особые вопросы, которые следует учитывать при включаемой Корпоративная голосовая связь локальной сети</span><span class="sxs-lookup"><span data-stu-id="fe773-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="fe773-122">В некоторых случаях может потребоваться изменить способ, позволяющий пользователям Корпоративная голосовая связь убедиться, что они могут успешно делать и принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="fe773-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="fe773-123">Если в развертывании имеются пользователи, которые соответствуют следующим условиям, выполните действия, включенные в этот список, чтобы включить для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="fe773-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="fe773-124">Если пользователь создается в локальной среде AD, а затем синхронизируется со Skype для бизнеса Online без включения Skype для бизнеса или для Корпоративная голосовая связь и у него нет набора LineURI, запустите для каждого затронутого пользователя следующие cmdlets, заменив значения фактическими значениями для вашей \< \> среды:</span><span class="sxs-lookup"><span data-stu-id="fe773-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="fe773-125">Если для пользователя уже включена возможность локальной работы Skype для бизнеса, но ему не был включен доступ к Корпоративная голосовая связь или ему не был назначен LineURI, прежде чем он будет перемещен в Skype для бизнеса Online, запустите для каждого пользователя следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fe773-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="fe773-126">Если пользователь уже включен в локальной сети Skype для бизнеса, но не включен для Корпоративная голосовая связь, даже если он уже назначен LineURI, запустите следующий cmdlet для каждого затронутого пользователя:</span><span class="sxs-lookup"><span data-stu-id="fe773-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


