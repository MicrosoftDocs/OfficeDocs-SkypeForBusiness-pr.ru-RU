---
title: Необходимые условия и права пользователя для настройки групповой отправки звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1f5387ac7c67e01e3c4473367e1256cf07181a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="72e26-102">Требования к настройке группового ответа на звонки и пользовательские права в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e26-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72e26-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="72e26-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="72e26-104">Групповое получение вызовов — это функция управления звонками, устанавливаемая по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="72e26-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="72e26-105">В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить раскладки группового ответа и права пользователя, необходимые для выполнения задач по настройке.</span><span class="sxs-lookup"><span data-stu-id="72e26-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="72e26-106">В этом разделе предполагается, что вы читали документацию по планированию, связанную с групповой Отделом ответа на звонки (см. [планирование группового ответа на звонки в Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="72e26-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="72e26-107">Предварительные требования к настройке групповой отправки звонков</span><span class="sxs-lookup"><span data-stu-id="72e26-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="72e26-108">Для групповой отправки звонков требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="72e26-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="72e26-109">служба приложения;</span><span class="sxs-lookup"><span data-stu-id="72e26-109">Application service</span></span>

  - <span data-ttu-id="72e26-110">Приложение "Парковка вызовов"</span><span class="sxs-lookup"><span data-stu-id="72e26-110">Call Park application</span></span>

<span data-ttu-id="72e26-111">Эти компоненты устанавливаются автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="72e26-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="72e26-112">Права пользователя настройки групповой отправки звонков</span><span class="sxs-lookup"><span data-stu-id="72e26-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="72e26-113">Для настройки групповой отправки звонков используются следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="72e26-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="72e26-114">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="72e26-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="72e26-115">SEFAUtil Resource Kit Tool</span><span class="sxs-lookup"><span data-stu-id="72e26-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="72e26-116">Используйте командную консоль Lync Server для создания групп ответа на звонки в таблице орбит парковки вызовов и управления ими.</span><span class="sxs-lookup"><span data-stu-id="72e26-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="72e26-117">Используйте средство SEFAUtil Resource Kit Tool, чтобы назначить группу ответа на звонки, а также включить групповую отправке звонков для пользователей или отключать групповую откадровую связь для пользователей.</span><span class="sxs-lookup"><span data-stu-id="72e26-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="72e26-118">Для настройки групповой отправки вызовов требуется любая из следующих административных ролей в зависимости от задачи:</span><span class="sxs-lookup"><span data-stu-id="72e26-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="72e26-119">**CsVoiceAdministrator:** Эта роль администратора позволяет создавать, настраивать и управлять всеми параметрами и политиками, связанными с голосовыми сообщениями.</span><span class="sxs-lookup"><span data-stu-id="72e26-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="72e26-120">**CsUserAdministrator:** Эта роль администратора позволяет пользователям предоставлять групповые звонки для пользователей.</span><span class="sxs-lookup"><span data-stu-id="72e26-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="72e26-121">Она также имеет доступ только для чтения ко всем параметрам конфигурации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="72e26-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="72e26-122">**CsServerAdministrator:** Эта роль администратора позволяет управлять серверами и службами, а также отслеживать их и устранять неполадки.</span><span class="sxs-lookup"><span data-stu-id="72e26-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="72e26-123">**CsAdministrator:** Эта роль администратора позволяет выполнять все задачи CsVoiceAdministrator, CsServerAdministrator и CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="72e26-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="72e26-124">Подробные сведения об административных правах приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="72e26-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72e26-125">См. также</span><span class="sxs-lookup"><span data-stu-id="72e26-125">See Also</span></span>


[<span data-ttu-id="72e26-126">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e26-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="72e26-127">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e26-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

