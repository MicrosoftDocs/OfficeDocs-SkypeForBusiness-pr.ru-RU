---
title: Перемещение оставшихся пользователей
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Вы можете переместить пользователей на новый сервер 2019 для развертывания Skype для бизнеса Server, используя панель управления Skype для бизнеса Server или консоль управления Skype для бизнеса Server. Чтобы обеспечить плавный переход на Skype для бизнеса Server 2019, необходимо соблюдать определенные требования. Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этом разделе, можно найти в статье Настройка миграции клиентов. Подробное руководство по перемещению пользователей описано в разделе Этап 4: перемещение тестовых пользователей в пилотный пул.'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813267"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="df08c-106">Перемещение оставшихся пользователей в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="df08c-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="df08c-107">Вы можете переместить пользователей на новый сервер 2019 для развертывания Skype для бизнеса Server, используя панель управления Skype для бизнеса Server или консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="df08c-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="df08c-108">Чтобы обеспечить плавный переход на Skype для бизнеса Server 2019, необходимо соблюдать определенные требования.</span><span class="sxs-lookup"><span data-stu-id="df08c-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="df08c-109">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этом разделе, можно найти в статье [Настройка миграции клиентов](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="df08c-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="df08c-110">Подробное руководство по перемещению пользователей описано в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="df08c-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="df08c-111">Для перемещения пользователей из устаревшей среды в Skype для бизнеса Server 2019 нельзя использовать оснастку "пользователи и компьютеры Active Directory" и стандартные средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="df08c-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="df08c-112">Когда пользователь перемещается в пул 2019 в Skype для бизнеса Server, данные для пользователя перемещаются в серверную базу данных, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="df08c-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="df08c-113">Сюда входят активные собрания, созданные устаревшим пользователем.</span><span class="sxs-lookup"><span data-stu-id="df08c-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="df08c-114">Например, если пользователь с устаревшим подключением настроил **Конференц-** связь, она будет доступна в новом пуле 2019 в Skype для бизнеса Server после того, как пользователь будет перемещен.</span><span class="sxs-lookup"><span data-stu-id="df08c-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="df08c-115">Сведения о том, как получить доступ к собранию, будут по-прежнему совпадать с **URL-адресом Конференции и идентификатором конференции**.</span><span class="sxs-lookup"><span data-stu-id="df08c-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="df08c-116">Единственная разница заключается в том, что Конференция теперь размещена в пуле Skype для бизнеса Server 2019, а не в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="df08c-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="df08c-117">Пользователи в сети Skype для бизнеса Server 2019 не требуют развертывания обновленных клиентов одновременно.</span><span class="sxs-lookup"><span data-stu-id="df08c-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="df08c-118">Новые функции будут доступны пользователям только в том случае, если они обновлены до нового клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="df08c-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="df08c-119">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="df08c-119">Post migration task</span></span>

1. <span data-ttu-id="df08c-120">После перемещения пользователей убедитесь, что им назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="df08c-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="df08c-121">Чтобы убедиться в том, что пользователи, организованные в Skype для бизнеса Server 2019, тесно взаимодействуют с федеративными пользователями, которые размещаются на устаревшей установке, политика конференц-связи, назначенная для мигрировавших пользователей, должна разрешить анонимным участникам.</span><span class="sxs-lookup"><span data-stu-id="df08c-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="df08c-122">Политики Конференции, разрешающие анонимным участникам разрешение **на приглашение** анонимных пользователей, выделены на панели управления в Skype для бизнеса Server 2019, и в выходных данных командлета **Get-КсконференЦингполици** в командной консоли Skype для Business Server **аллованонимауспартиЦипантсинмитингс** значение **true** .</span><span class="sxs-lookup"><span data-stu-id="df08c-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

