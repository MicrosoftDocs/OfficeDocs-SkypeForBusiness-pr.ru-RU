---
title: Необходимые условия и разрешения для настройки конференц-связи с телефонным подключением
description: Необходимые условия и разрешения для настройки конференц-связи с телефонным подключением.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576175"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="e6c06-103">Необходимые условия и разрешения для настройки конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6c06-103">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6c06-104">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e6c06-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e6c06-105">Конференц-связь с телефонным подключением является опциональным компонентом рабочей нагрузки для конференц-связи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6c06-105">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="e6c06-106">Компоненты, которые необходимо установить перед настройкой конференц-связи с телефонным подключением, развертываются при использовании построителя топологий для создания топологии и последующего настройки пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6c06-106">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="e6c06-107">В этом разделе описывается подготовка к настройке конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-107">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="e6c06-108">Предполагается, что вы прочли разделы по планированию, в частности разделы по рабочей нагрузке "Конференция" и конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-108">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="e6c06-109">Компоненты, требуемые для настройки конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e6c06-109">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="e6c06-110">Для конференц-связи с телефонным подключением требуются следующие компоненты Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e6c06-110">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="e6c06-111">Unified Communications Application Service (UCAS) (называемые *службой приложения*);</span><span class="sxs-lookup"><span data-stu-id="e6c06-111">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="e6c06-112">приложение "Помощник по конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="e6c06-112">Conferencing Attendant application</span></span>

  - <span data-ttu-id="e6c06-113">приложение "Объявления для конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="e6c06-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="e6c06-114">веб-страница "Параметры конференц-связи с телефонным подключением";</span><span class="sxs-lookup"><span data-stu-id="e6c06-114">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="e6c06-115">По крайней мере один сервер-посредник сервера Lync Server 2013 и по крайней мере один шлюз PSTN</span><span class="sxs-lookup"><span data-stu-id="e6c06-115">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="e6c06-116">Эти компоненты развертываются при использовании построителя топологий для определения и публикации топологии, а затем развертывания интерфейсного пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6c06-116">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="e6c06-117">При развертывании корпоративной голосовой связи ее необходимо развернуть перед настройкой конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-117">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="e6c06-118">Если вы не развертываете корпоративную голосовую связь, вы можете развернуть сервер-посредник и шлюз телефонной сети общего пользования (PSTN) при развертывании пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6c06-118">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e6c06-119">При обновлении с Office Communications Server 2007 R2 до Lync Server 2013 развертывайте Конференц-связь с телефонным подключением в каждом пуле, который планируется использовать для размещения конференций Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6c06-119">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="e6c06-120">Дополнительные сведения о миграции конференц-связи с телефонным подключением см. в разделе <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e6c06-120">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e6c06-121">Содержимое этого раздела предполагает, что вы выполнили следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e6c06-121">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="e6c06-122">Применяет последние обновления к среде Office Communications Server 2007 R2 при переходе на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6c06-122">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="e6c06-123">Использование построителя топологий для создания и настройки топологии.</span><span class="sxs-lookup"><span data-stu-id="e6c06-123">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="e6c06-124">При указании рабочей нагрузки "Конференция" необходимо выбрать конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-124">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="e6c06-125">Подробнее об определении топологии можно узнать в статье [Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e6c06-125">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e6c06-126">Публикация топологии и настройка интерфейсного пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6c06-126">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="e6c06-127">Сведения о публикации топологии и установке Lync Server 2013 приведены в статье Deployment [Lync server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e6c06-127">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e6c06-128">При установке опубликованной топологии веб-страница "Параметры конференц-связи с телефонным подключением" устанавливается на сервере переднего плана или сервере Standard Edition в ходе установки веб-служб.</span><span class="sxs-lookup"><span data-stu-id="e6c06-128">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e6c06-129">Если изменить путь к хранилищу файлов в построителе топологий после развертывания Lync Server 2013, необходимо перезапустить помощника по конференц-связи и конференц-извещений для использования нового пути.</span><span class="sxs-lookup"><span data-stu-id="e6c06-129">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="e6c06-130">Развернутая Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="e6c06-130">Deployed Enterprise Voice.</span></span> <span data-ttu-id="e6c06-131">Если вы не развертываете корпоративную голосовую связь, вы либо развернули сервер-посредник на сервере переднего плана Enterprise Edition или на сервере Standard Edition, либо развернули автономный сервер-посредник и развернули шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6c06-131">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="e6c06-132">Подробнее о развертывании корпоративной голосовой связи можно узнать в статье Deployment [Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e6c06-132">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="e6c06-133">Сведения об установке автономного сервера-посредника и шлюза PSTN приведены в статье Deployment Server- [посредники и определение одноранговых узлов в Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e6c06-133">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e6c06-134">На следующей блок-схеме показаны шаги, которые необходимо выполнить перед настройкой конференц-связи с телефонным подключением, а также для настройки конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-134">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="e6c06-135">**Развертывание конференц-связи с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="e6c06-135">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="e6c06-136">![Блок-схема развертывания конференц-связи с телефонным подключением](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Блок-схема развертывания конференц-связи с телефонным подключением")</span><span class="sxs-lookup"><span data-stu-id="e6c06-136">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="e6c06-137">Разрешения для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e6c06-137">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="e6c06-138">Для настройки конференц-связи с телефонным подключением вам потребуются следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="e6c06-138">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="e6c06-139">Панель управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6c06-139">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="e6c06-140">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="e6c06-140">Lync Server Management Shell</span></span>

<span data-ttu-id="e6c06-141">С помощью этих средств администрирования вы сможете настроить параметры конференц-связи с телефонным подключением, а также абонентские группы, политики и прочие параметры, требуемые конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e6c06-141">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="e6c06-142">Для настройки конференц-связи с телефонным подключением потребуются следующие административные роли (в зависимости от задачи):</span><span class="sxs-lookup"><span data-stu-id="e6c06-142">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="e6c06-143">**CsVoiceAdministrator**     Эта роль администратора позволяет создавать и настраивать параметры и политики, связанные с голосовыми сообщениями, а также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="e6c06-143">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="e6c06-144">**CsUserAdministrator**     Эта роль администратора позволяет включать и отключать пользователей для Lync Server, а также назначать существующие политики, такие как политики конференц-связи и политики ПИН-кодов, пользователям.</span><span class="sxs-lookup"><span data-stu-id="e6c06-144">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="e6c06-145">**CsAdministrator**     Эта роль администратора позволяет выполнять все задачи CsVoiceAdministrator и CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e6c06-145">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6c06-146">См. также</span><span class="sxs-lookup"><span data-stu-id="e6c06-146">See Also</span></span>


[<span data-ttu-id="e6c06-147">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6c06-147">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

