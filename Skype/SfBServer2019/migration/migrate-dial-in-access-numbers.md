---
title: Перенос номеров доступа
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перенос номеров доступа Скайп для Business Server 2019 требуется выполнение командлета Move-CsApplicationEndpoint для переноса контактных объектов. Во время установки прежних версий и Скайп для периода сосуществования Business Server 2019 номера для телефонного номера, созданные в Скайп Business Server 2019 ведут себя аналогично на номера доступа, создаваемого в прежних версий установка, как описано в данном раздел.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027727"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="1dcd0-104">Перенос номеров доступа</span><span class="sxs-lookup"><span data-stu-id="1dcd0-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="1dcd0-105">Перенос номеров доступа Скайп для Business Server 2019 требуется выполнение командлета **Move-CsApplicationEndpoint** для переноса контактных объектов.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="1dcd0-106">Во время установки прежних версий и Скайп для периода сосуществования Business Server 2019 номера для телефонного номера, созданные в Скайп Business Server 2019 ведут себя аналогично на номера доступа, создаваемого в прежних версий установка, как описано в данном раздел.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 
  
<span data-ttu-id="1dcd0-107">Номера для телефонного номера, созданные в устаревший установите, но перемещено в Скайп для Business Server 2019 или, которые созданы в Скайп для 2019 Business Server до, во время и после миграции, обладают следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="1dcd0-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>
  
- <span data-ttu-id="1dcd0-108">Не отображаются на странице номеров телефонного подключения и приглашения на собрание Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="1dcd0-109">Отображаются на странице номеров телефонного подключения и установки устаревших приглашений на собрания.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="1dcd0-110">Отображаются на Скайп для Business Server 2019 приглашения на собрания и на странице номеров телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="1dcd0-111">Не могут просматривать или изменять в средстве администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>
    
- <span data-ttu-id="1dcd0-112">Можно просматривать и изменять в прежних версий install панель управления и устаревшие установить консоль управления.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>
    
- <span data-ttu-id="1dcd0-113">Можно просматривать и изменять в Скайп для панели управления 2019 Business Server и Скайп для консоли 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>
    
- <span data-ttu-id="1dcd0-114">Их можно повторно упорядочивать внутри региона с помощью командлета Set-CsDialinConferencingAccessNumber с параметром Priority.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>
    
<span data-ttu-id="1dcd0-115">Необходимо завершить перенос номеров доступа, указывающие на устаревший установку пула до его ликвидации прежних версий install.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="1dcd0-116">Если не выполнить миграции номеров доступа, как описано в следующей процедуре, входящие звонки для номера доступа завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1dcd0-117">Необходимо выполнить эту процедуру до ликвидации пула прежних версий install.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1dcd0-118">Рекомендуется переместить номера доступа при незначительном использовании небольшим, это на случай короткого периода недоступности службы.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="1dcd0-119">Определение и перемещение номера для телефонного номера</span><span class="sxs-lookup"><span data-stu-id="1dcd0-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="1dcd0-120">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1dcd0-121">Чтобы переместить каждый номер доступа в пул, размещенный в Скайп для Business Server 2019, с помощью командной строки выполните:</span><span class="sxs-lookup"><span data-stu-id="1dcd0-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. <span data-ttu-id="1dcd0-122">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-122">Open Skype for Business Server Control Panel.</span></span>
    
4. <span data-ttu-id="1dcd0-123">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-123">In the left navigation bar, click **Conferencing**.</span></span>
    
5. <span data-ttu-id="1dcd0-124">Перейдите на вкладку **Телефонный номер доступа** .</span><span class="sxs-lookup"><span data-stu-id="1dcd0-124">Click the **Dial-in Access Number** tab.</span></span> 
    
6. <span data-ttu-id="1dcd0-125">Убедитесь, что номера для телефонного номера осталось для пула прежних версий установки, из которого выполняется миграция.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1dcd0-126">Когда все номера доступа выберите команду Скайп для пула Business Server 2019, вы можете ликвидировать пул прежних версий install.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1dcd0-127">Проверка миграции номеров доступа с помощью Скайп для панели управления сервера Business</span><span class="sxs-lookup"><span data-stu-id="1dcd0-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1dcd0-128">Из учетной записи пользователя, назначенной роли **CsUserAdministrator** или **csadministrator** Войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="1dcd0-129">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-129">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1dcd0-130">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-130">In the left navigation bar, click **Conferencing**.</span></span>
    
4. <span data-ttu-id="1dcd0-131">Перейдите на вкладку **Телефонный номер доступа** .</span><span class="sxs-lookup"><span data-stu-id="1dcd0-131">Click the **Dial-in Access Number** tab.</span></span> 
    
5. <span data-ttu-id="1dcd0-132">Убедитесь, что все номера доступа перенесены в пул, размещенный на Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1dcd0-133">Проверка миграции номеров доступа, с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1dcd0-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1dcd0-134">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-134">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="1dcd0-135">Чтобы вернуть все номера доступа к конференц связи с телефонным перенесены из командной строки выполните:</span><span class="sxs-lookup"><span data-stu-id="1dcd0-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. <span data-ttu-id="1dcd0-136">Убедитесь, что все номера доступа перенесены в пул, размещенный на Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1dcd0-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    

