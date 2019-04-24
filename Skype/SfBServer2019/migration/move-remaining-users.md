---
title: Перемещение оставшихся пользователей
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Можно переместить пользователей в новые Скайп для развертывания Business Server 2019 с помощью любого из Скайп для панели управления Business Server или Скайп для консоли Business Server. То необходимо выполнить некоторые требования, чтобы обеспечить плавный переход к Скайп для Business Server 2019. Для получения дополнительных сведений о предварительных требованиях для выполнения процедур, описанных в данном разделе увидеть Настройка клиентов для миграции. Подробное описание действий о перемещении пользователей, посвященной этап 4: перемещение тестовых пользователей в пилотный пул.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231590"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="e2fbe-106">Перемещение оставшихся пользователей на Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e2fbe-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="e2fbe-107">Можно переместить пользователей в новые Скайп для развертывания Business Server 2019 с помощью любого из Скайп для панели управления Business Server или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e2fbe-108">То необходимо выполнить некоторые требования, чтобы обеспечить плавный переход к Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="e2fbe-109">Для получения дополнительных сведений о предварительных требованиях для выполнения процедур, описанных в данном разделе увидеть [Настройка клиентов для миграции](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="e2fbe-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="e2fbe-110">Подробное описание действий о перемещении пользователей в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e2fbe-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2fbe-111">Для перемещения пользователей из старой среды Скайп Business Server 2019 нельзя использовать оснастку Active Directory — пользователи и компьютеры или устаревшие средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="e2fbe-112">При перемещении пользователя в Скайп для пула Business Server 2019 данные пользователя перемещаются серверной базы данных, связанный с этим новым пулом.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e2fbe-113">Этот компонент включает active собраний, создаваемые пользователем прежних версий.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="e2fbe-114">Например если указанные конференции **совещанию** прежних версий пользователем этой конференции по-прежнему будут доступны в новых Скайп для пула Business Server 2019 после перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="e2fbe-115">Подробные сведения для доступа к этой собрания будут по-прежнему ту же **конференции URL-адрес и идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="e2fbe-116">Единственное отличие — теперь размещена конференции в Скайп для пула Business Server 2019, а не в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e2fbe-117">Ящиков пользователей на Скайп for Business Server 2019 не требуется развернуть обновленную клиенты в то же время.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="e2fbe-118">Новые функциональные возможности будут доступны пользователям только в том случае, если они требуется обновление до нового клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="e2fbe-119">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="e2fbe-119">Post migration task</span></span>

1. <span data-ttu-id="e2fbe-120">После перемещения пользователей убедитесь политики конференц-связи, назначенной им.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="e2fbe-121">Чтобы организованы пользователям, размещенными на Скайп для Business Server 2019 могли работать с собраниями федеративные пользователи, которые размещаются на прежних версий install, политика конференц-связи, назначенная для перенесенных пользователей, должна поддерживать анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="e2fbe-122">Для политик конференц-связи, анонимных участников **Разрешить участникам приглашать анонимных пользователей** , выбранных в Скайп для панели управления 2019 Business Server и иметь **AllowAnonymousParticipantsInMeetings** в значение **True** Вывод командлета **Get-CsConferencingPolicy** в Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2fbe-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

