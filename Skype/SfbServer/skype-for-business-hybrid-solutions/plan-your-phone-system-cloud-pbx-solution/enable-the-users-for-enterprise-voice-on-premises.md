---
title: Включение пользователей для корпоративной голосовой связи локально
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Пользователи могут с помощью телефонной системой в Office 365 (облако УАТС) необходимо включить их для корпоративной голосовой связи и назначить их номер телефона. Это можно сделать с помощью локального развертывания, пока пользователь по-прежнему размещенный в локальном развертывании.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657449"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="89c6c-104">Включение пользователей для корпоративной голосовой связи локально</span><span class="sxs-lookup"><span data-stu-id="89c6c-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="89c6c-105">Пользователи могут с помощью телефонной системой в Office 365 (облако УАТС) необходимо включить их для корпоративной голосовой связи и назначить их номер телефона.</span><span class="sxs-lookup"><span data-stu-id="89c6c-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="89c6c-106">Это можно сделать с помощью локального развертывания, пока пользователь по-прежнему размещенный в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="89c6c-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="89c6c-107">Чтобы разрешить пользователям работу с корпоративной голосовой связи на локальном и назначить номер телефона</span><span class="sxs-lookup"><span data-stu-id="89c6c-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="89c6c-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="89c6c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89c6c-109">Откройте панель управления Skype для бизнеса Server, используя меню "Пуск" или ярлык на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="89c6c-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="89c6c-110">Кроме того, можно открыть окно браузера и ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="89c6c-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89c6c-111">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="89c6c-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="89c6c-112">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="89c6c-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="89c6c-113">В таблице щелкните Скайп для бизнеса в Интернет учетная запись пользователя, необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="89c6c-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="89c6c-114">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="89c6c-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="89c6c-115">В разделе **Телефония** щелкните **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="89c6c-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="89c6c-p103">Щелкните **URI строки** и введите уникальный нормализованный номер телефона (например, tel:+14255550200). Затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="89c6c-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="89c6c-118">Что необходимо учитывать при включении пользователей корпоративной голосовой связи локально</span><span class="sxs-lookup"><span data-stu-id="89c6c-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="89c6c-119">В некоторых случаях может потребоваться изменить способ предоставления пользователям доступа к корпоративной голосовой связи, чтобы они могли успешно звонить и принимать вызовы.</span><span class="sxs-lookup"><span data-stu-id="89c6c-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="89c6c-120">Если у пользователей в развертывании, которые соответствуют условиям, выполните действия, включенные для включения пользователя для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="89c6c-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="89c6c-121">Если пользователь будет создан в своей локальной AD и синхронизации с Скайп для бизнеса в Интернет без включаемого для Скайп для бизнеса или для корпоративной голосовой связи и нет LineURI значение, выполните следующие командлеты для каждого соответствующего пользователя, заменив значения в < C0 настроек <b1></b1> с фактических значений для вашей среды:</span><span class="sxs-lookup"><span data-stu-id="89c6c-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="89c6c-122">Если пользователь уже включен для Скайп для бизнеса локально, но не был включен для корпоративной голосовой связи или назначенных LineURI перед перемещается в Скайп для бизнеса в Интернет, выполните следующий командлет для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="89c6c-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="89c6c-123">Если пользователь уже включен в Скайп для бизнеса локально, но не включен для корпоративной голосовой связи, даже в том случае, если они уже назначены LineURI, выполните следующий командлет для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="89c6c-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


