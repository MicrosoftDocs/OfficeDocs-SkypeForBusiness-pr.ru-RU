---
title: Перенос номеров доступа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Для миграции номеров доступа для телефонного подключения в Skype для бизнеса Server 2019 необходимо запустить командлет Move-Ксаппликатионендпоинт, чтобы перенести объекты контакта. В течение срока сосуществования устаревшей установки и Skype для бизнеса Server 2019 номера доступа для телефонного подключения, созданные в Skype для бизнеса Server 2019, будут вести себя так же, как и номера доступа для телефонного подключения, которые вы создаете в предыдущей установке, как описано в этой секци.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991144"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c6af6-104">Перенос номеров доступа</span><span class="sxs-lookup"><span data-stu-id="c6af6-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="c6af6-105">Для миграции номеров доступа для телефонного подключения в Skype для бизнеса Server 2019 необходимо запустить командлет **Move-ксаппликатионендпоинт** , чтобы перенести объекты контакта.</span><span class="sxs-lookup"><span data-stu-id="c6af6-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="c6af6-106">В течение срока сосуществования устаревшей установки и Skype для бизнеса Server 2019 номера доступа для телефонного подключения, созданные в Skype для бизнеса Server 2019, будут вести себя так же, как и номера доступа для телефонного подключения, которые вы создаете в предыдущей установке, как описано в этой секци.</span><span class="sxs-lookup"><span data-stu-id="c6af6-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="c6af6-107">Номера доступа для телефонного подключения, созданные в устаревшей версии, но перенесенные в Skype для бизнеса Server 2019 или созданные в Skype для бизнеса Server 2019 до, во время или после миграции, обладают следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="c6af6-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="c6af6-108">Не отображаются в приглашениях на собрание Office Communications Server 2007 R2 и на странице номера доступа для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="c6af6-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c6af6-109">Отображаются в приглашениях на собрания и на странице номер доступа для подключения к удаленным версиям.</span><span class="sxs-lookup"><span data-stu-id="c6af6-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c6af6-110">Отображаются в приглашениях на собрания в Skype для бизнеса Server 2019 и на странице номера доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="c6af6-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c6af6-111">В средстве администрирования Office Communications Server 2007 R2 нельзя просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="c6af6-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="c6af6-112">Можно просмотреть и изменить на устаревшей панели управления установкой и в командной консоли установки устаревшей версии.</span><span class="sxs-lookup"><span data-stu-id="c6af6-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="c6af6-113">Можно просмотреть и изменить на панели управления Skype для бизнеса Server 2019 и в командной консоли Skype для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6af6-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="c6af6-114">Возможность повторной последовательности в регионе с помощью командлета Set-КсдиалинконференЦингакцесснумбер с параметром priority.</span><span class="sxs-lookup"><span data-stu-id="c6af6-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="c6af6-115">Перед списанием устаревшего пула установки необходимо завершить перенос номеров доступа для телефонного подключения, указывающих на устаревший пул установки.</span><span class="sxs-lookup"><span data-stu-id="c6af6-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="c6af6-116">Если вы не закончите перенос номеров доступа для телефонного подключения, как описано в приведенной ниже процедуре, входящие звонки на номера доступа завершатся сбоем.</span><span class="sxs-lookup"><span data-stu-id="c6af6-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6af6-117">Эту процедуру необходимо выполнить перед списанием устаревшего пула установки.</span><span class="sxs-lookup"><span data-stu-id="c6af6-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="c6af6-118">Мы рекомендуем вам перемещать номера доступа для телефонного подключения при низком использовании сети в случае короткого периода простоя службы.</span><span class="sxs-lookup"><span data-stu-id="c6af6-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="c6af6-119">Для идентификации и перемещения номеров доступа с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="c6af6-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="c6af6-120">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="c6af6-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c6af6-121">Чтобы переместить номер доступа для телефонного подключения в пул, размещенный в Skype для бизнеса Server 2019, в командной строке выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c6af6-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="c6af6-122">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c6af6-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="c6af6-123">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="c6af6-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="c6af6-124">Откройте вкладку **номер доступа для телефонного подключения** .</span><span class="sxs-lookup"><span data-stu-id="c6af6-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="c6af6-125">Убедитесь, что для устаревшего пула, из которого выполняется миграция, не сохраняются номера доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="c6af6-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c6af6-126">Если все номера доступа для телефонного подключения указывают на пул 2019 в Skype для бизнеса Server, вы можете затем списать устаревший пул установки.</span><span class="sxs-lookup"><span data-stu-id="c6af6-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c6af6-127">Проверка миграции номеров доступа для телефонного подключения с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c6af6-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c6af6-128">Из учетной записи пользователя, которой назначена роль **ксусерадминистратор** или роль **ксадминистратор** , войдите на любой компьютер во внутренней среде.</span><span class="sxs-lookup"><span data-stu-id="c6af6-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="c6af6-129">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c6af6-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c6af6-130">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="c6af6-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="c6af6-131">Откройте вкладку **номер доступа для телефонного подключения** .</span><span class="sxs-lookup"><span data-stu-id="c6af6-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="c6af6-132">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6af6-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c6af6-133">Проверка миграции номеров доступа для телефонного подключения с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c6af6-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c6af6-134">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c6af6-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="c6af6-135">Чтобы вернуть все номера доступа для конференц-связи с телефонным подключением, перенесенные из командной строки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c6af6-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="c6af6-136">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6af6-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


