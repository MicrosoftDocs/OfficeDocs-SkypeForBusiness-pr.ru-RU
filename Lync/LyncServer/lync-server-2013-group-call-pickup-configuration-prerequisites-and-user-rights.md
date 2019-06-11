---
title: Необходимые условия для настройки раскладки группового звонка и права пользователей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2eb0af5b78d5d391ba055e557ad71da79484b5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="ba09b-102">Необходимые условия для настройки раскладки группового звонка и права пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba09b-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba09b-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ba09b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ba09b-104">Отправка группового звонка — это функция управления звонками, которая устанавливается по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ba09b-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ba09b-105">В этой статье описаны действия, которые необходимо выполнить перед настройкой отправки групповых звонков и правами пользователей, которые необходимо выполнить для выполнения задач настройки.</span><span class="sxs-lookup"><span data-stu-id="ba09b-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="ba09b-106">В этом разделе предполагается, что вы прочитали документацию по планированию, связанную с получением группового звонка (см. раздел [Планирование отправки групп в Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="ba09b-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="ba09b-107">Требования для настройки раскладки группового звонка</span><span class="sxs-lookup"><span data-stu-id="ba09b-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="ba09b-108">Для отправки групповых звонков требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ba09b-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="ba09b-109">приложения</span><span class="sxs-lookup"><span data-stu-id="ba09b-109">Application service</span></span>

  - <span data-ttu-id="ba09b-110">приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="ba09b-110">Call Park application</span></span>

<span data-ttu-id="ba09b-111">Эти компоненты устанавливаются автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ba09b-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="ba09b-112">Права пользователя на настройку раскладки группового звонка</span><span class="sxs-lookup"><span data-stu-id="ba09b-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="ba09b-113">Для настройки отправки группового звонка используются следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="ba09b-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="ba09b-114">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba09b-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="ba09b-115">Инструмент "набор ресурсов Сефаутил"</span><span class="sxs-lookup"><span data-stu-id="ba09b-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="ba09b-116">Используйте командную консоль Lync Server для создания групп отправки звонков и управления ими в таблице "приостановить Звонок".</span><span class="sxs-lookup"><span data-stu-id="ba09b-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="ba09b-117">С помощью средства Сефаутил Resource Kit вы можете назначить группу для подбора звонков, а также включить или отключить функцию отправки групп для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba09b-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="ba09b-118">Для настройки отправки группового вызова требуются следующие административные роли в зависимости от задачи.</span><span class="sxs-lookup"><span data-stu-id="ba09b-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="ba09b-119">**Ксвоицеадминистратор:** Эта роль администратора может создавать, настраивать и управлять всеми параметрами и политиками, связанными с голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="ba09b-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="ba09b-120">**Ксусерадминистратор:** Эта роль администратора может активировать раскладки групповых звонков для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba09b-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="ba09b-121">Эта роль администратора также имеет доступ к просмотру только для чтения для всех конфигураций голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ba09b-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="ba09b-122">**Кссерверадминистратор:** Эта роль администратора может управлять работой серверов и служб, а также отслеживать их и устранять неполадки.</span><span class="sxs-lookup"><span data-stu-id="ba09b-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="ba09b-123">**Ксадминистратор:** Эта роль администратора может выполнять все задачи Ксвоицеадминистратор, Кссерверадминистратор и Ксусерадминистратор.</span><span class="sxs-lookup"><span data-stu-id="ba09b-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ba09b-124">Подробные сведения о правах администратора можно найти <A href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ba09b-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba09b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ba09b-125">See Also</span></span>


[<span data-ttu-id="ba09b-126">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba09b-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="ba09b-127">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba09b-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

