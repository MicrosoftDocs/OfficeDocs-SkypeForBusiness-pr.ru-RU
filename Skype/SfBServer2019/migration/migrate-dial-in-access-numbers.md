---
title: Перенос номеров для телефонного подключения
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Для переноса номеров доступа с телефонным доступом в Skype для бизнеса Server 2019 требуется запуск Move-CsApplicationEndpoint для переноса контактных объектов. Во время устаревшей установки и сосуществования Skype для бизнеса Server 2019 номера доступа с телефонным доступом, созданные в Skype для бизнеса Server 2019, ведут себя аналогично номерам доступа для телефонного доступа, созданным в устаревшей установке, как описано в этом разделе.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752701"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="f6422-104">Перенос номеров для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="f6422-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="f6422-105">Для переноса номеров доступа с телефонным доступом в Skype для бизнеса Server 2019 необходимо использовать для переноса контактных объектов с помощью cmdlet **Move-CsApplicationEndpoint.**</span><span class="sxs-lookup"><span data-stu-id="f6422-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="f6422-106">Во время устаревшей установки и сосуществования Skype для бизнеса Server 2019 номера доступа с телефонным доступом, созданные в Skype для бизнеса Server 2019, ведут себя аналогично номерам доступа для телефонного доступа, созданным в устаревшей установке, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f6422-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="f6422-107">Номера доступа для телефонного доступа, созданные в устаревшей установке, но перенесенные в Skype для бизнеса Server 2019 или созданные в Skype для бизнеса Server 2019 до, во время или после миграции, имеют следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="f6422-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="f6422-108">не отображаются в приглашениях на собрание Office Communications Server 2007 R2  и на странице номеров телефонного подключения;</span><span class="sxs-lookup"><span data-stu-id="f6422-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f6422-109">Появится на устаревшей странице приглашений на установку собраний и на странице телефонного номера доступа.</span><span class="sxs-lookup"><span data-stu-id="f6422-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f6422-110">Отображаться в приглашениях на собрания Skype для бизнеса Server 2019 и на странице телефонного номера доступа.</span><span class="sxs-lookup"><span data-stu-id="f6422-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f6422-111">их нельзя просматривать или изменять в средстве администрирования Office Communications Server 2007 R2;</span><span class="sxs-lookup"><span data-stu-id="f6422-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="f6422-112">Можно просматривать и изменять в устаревшей панели управления установкой и в устаревшей оболочке управления установкой.</span><span class="sxs-lookup"><span data-stu-id="f6422-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="f6422-113">Можно просматривать и изменять в панели управления Skype для бизнеса Server 2019 и в оболочке управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6422-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="f6422-114">их можно повторно упорядочивать внутри региона с помощью командлета Set-CsDialinConferencingAccessNumber с параметром Priority.</span><span class="sxs-lookup"><span data-stu-id="f6422-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="f6422-115">Перед списанием устаревшего пула необходимо завершить перенос номеров доступа для телефонного доступа, которые указывают на устаревший пул установки.</span><span class="sxs-lookup"><span data-stu-id="f6422-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="f6422-116">Если вы не завершили миграцию телефонных номеров доступа, как описано в следующей процедуре, входящие вызовы на эти номера не будут работать.</span><span class="sxs-lookup"><span data-stu-id="f6422-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6422-117">Эту процедуру необходимо выполнить перед списанием устаревшего пула установки.</span><span class="sxs-lookup"><span data-stu-id="f6422-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="f6422-118">Рекомендуется переместить телефонные номера доступа при незначительном использовании сети на случай короткого периода недоступности службы.</span><span class="sxs-lookup"><span data-stu-id="f6422-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="f6422-119">Определение и перемещение телефонных номеров доступа</span><span class="sxs-lookup"><span data-stu-id="f6422-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="f6422-120">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Microsoft Skype для бизнеса Server **2019"** и щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="f6422-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f6422-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span><span class="sxs-lookup"><span data-stu-id="f6422-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="f6422-122">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f6422-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="f6422-123">В левой области навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="f6422-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="f6422-124">Перейдите на вкладку **Телефонный номер доступа**.</span><span class="sxs-lookup"><span data-stu-id="f6422-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="f6422-125">Убедитесь, что для устаревшего пула установки, из которого вы переносите, не осталось номеров доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="f6422-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6422-126">Когда все номера доступа для телефонного доступа указывают на пул Skype для бизнеса Server 2019, вы можете списание устаревшего пула установки.</span><span class="sxs-lookup"><span data-stu-id="f6422-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f6422-127">Проверка миграции телефонного номера доступа с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f6422-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f6422-128">В учетной записи пользователя, назначенной роли  **CsUserAdministrator** или **CsAdministrator**, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="f6422-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="f6422-129">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f6422-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f6422-130">В левой области навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="f6422-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="f6422-131">Перейдите на вкладку **Телефонный номер доступа**.</span><span class="sxs-lookup"><span data-stu-id="f6422-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="f6422-132">Убедитесь, что все номера доступа для телефонного доступа перенесены в пул, который был в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6422-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f6422-133">Проверка переноса номеров доступа с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f6422-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f6422-134">Откройте Skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6422-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f6422-135">Чтобы вернуть все перемещенные телефонные номера доступа к конференции в командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6422-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="f6422-136">Убедитесь, что все номера доступа для телефонного доступа перенесены в пул, который был в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6422-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


