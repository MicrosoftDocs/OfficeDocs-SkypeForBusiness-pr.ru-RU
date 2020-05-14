---
title: Разрешить локальным пользователям корпоративную голосовую связь
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
description: Чтобы пользователь использовал телефонную систему (облачная УАТС), необходимо сначала включить их для корпоративной голосовой связи и назначить им номер телефона. Это выполняется с помощью локального развертывания, когда пользователь по-прежнему размещается в локальном развертывании.
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221703"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="9bb24-104">Разрешить локальным пользователям корпоративную голосовую связь</span><span class="sxs-lookup"><span data-stu-id="9bb24-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="9bb24-105">Чтобы пользователь использовал телефонную систему (облачная УАТС), необходимо сначала включить их для корпоративной голосовой связи и назначить им номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9bb24-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="9bb24-106">Это выполняется с помощью локального развертывания, когда пользователь по-прежнему размещается в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="9bb24-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="9bb24-107">Включение локального пользователя для корпоративной голосовой связи и назначение номера телефона</span><span class="sxs-lookup"><span data-stu-id="9bb24-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="9bb24-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9bb24-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9bb24-109">Используйте меню "Пуск" или ярлык на рабочем столе, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9bb24-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="9bb24-110">Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9bb24-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9bb24-111">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="9bb24-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="9bb24-112">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="9bb24-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="9bb24-113">В таблице щелкните учетную запись пользователя Skype для бизнеса Online, которую необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9bb24-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="9bb24-114">В меню **Правка** выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9bb24-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="9bb24-115">В разделе **телефония**щелкните **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="9bb24-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="9bb24-116">Щелкните **URI строки**и введите уникальный нормализованный номер телефона (например, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="9bb24-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="9bb24-117">Затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9bb24-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="9bb24-118">Специальные рекомендации по включению локальных корпоративных голосовых служб для пользователей</span><span class="sxs-lookup"><span data-stu-id="9bb24-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="9bb24-119">В некоторых случаях может потребоваться изменить способ включения корпоративной голосовой связи для того, чтобы они могли успешно совершать и принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="9bb24-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="9bb24-120">Если у вас есть пользователи в развертывании, удовлетворяющие следующим условиям, выполните действия, описанные в статье Включение поддержки пользователя для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9bb24-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="9bb24-121">Если пользователь создается в локальной службе Active Directory, а затем синхронизируется с Skype для бизнеса Online без включения поддержки Skype для бизнеса или корпоративной голосовой связи и не имеет набора LineURI, выполните следующие командлеты для каждого затронутого пользователя, заменив значения на \< \> фактические значения для среды:</span><span class="sxs-lookup"><span data-stu-id="9bb24-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="9bb24-122">Если пользователь уже включил поддержку Skype для бизнеса в локальной среде, но не включился для корпоративной голосовой связи или назначил LineURI до перехода в Skype для бизнеса Online, выполните следующий командлет для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="9bb24-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="9bb24-123">Если пользователь уже включен в локальной среде Skype для бизнеса, но не включен для корпоративной голосовой связи, даже если уже назначен LineURI, выполните следующий командлет для каждого затронутого пользователя:</span><span class="sxs-lookup"><span data-stu-id="9bb24-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


