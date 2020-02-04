---
title: 'Lync Server 2013: определение и настройка топологии в средстве построения топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="598bb-102">Определение и настройка топологии в средстве построения топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="598bb-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="598bb-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="598bb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="598bb-104">В построителе топологии, определяющем новую топологию, или для изменения существующей топологии не требуется членство в группе локального администратора или привилегированного домена.</span><span class="sxs-lookup"><span data-stu-id="598bb-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="598bb-105">В построителе топологии вы можете выполнить необходимые действия по определению топологии для пула переднего плана Enterprise Edition или выпуска Standard Edition в соответствии с вашими требованиями к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="598bb-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="598bb-106">Для завершения и публикации топологии перед установкой Lync Server 2013 на серверах необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="598bb-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="598bb-107">Ниже описаны действия, которые необходимо выполнить, чтобы определить новую топологию.</span><span class="sxs-lookup"><span data-stu-id="598bb-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="598bb-108">Определение топологии</span><span class="sxs-lookup"><span data-stu-id="598bb-108">To define a topology</span></span>

1.  <span data-ttu-id="598bb-109">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="598bb-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="598bb-110">В построителе топологии выберите **создать топологию**.</span><span class="sxs-lookup"><span data-stu-id="598bb-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="598bb-111">Вам будет предложено указать расположение и имя файла для сохранения топологии.</span><span class="sxs-lookup"><span data-stu-id="598bb-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="598bb-112">Присвойте файлу топологии понятное имя и подтвердите расширение по умолчанию. тбксмл.</span><span class="sxs-lookup"><span data-stu-id="598bb-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="598bb-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="598bb-113">Click **OK**.</span></span>

3.  <span data-ttu-id="598bb-114">Перейдите в папку, в которой вы хотите сохранить XML-файл новой топологии, введите имя файла и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="598bb-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="598bb-115">На странице **Определение основного домена** введите имя основного домена SIP для своей организации, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="598bb-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="598bb-116">На странице **Укажите дополнительные домены** , введите имена дополнительных доменов, если таковые имеются, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="598bb-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="598bb-117">На странице **Определение первого сайта** введите имя и описание первого сайта, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="598bb-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="598bb-118">На странице **Укажите сведения о сайте** введите сведения о расположении для сайта, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="598bb-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="598bb-119">На странице **Новая топология успешно определена** страница, убедитесь, что установлен флажок **открыть мастер создания новых интерфейсов при закрытом** окне, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="598bb-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="598bb-120">После того как вы определили и сохранили топологию, используйте мастер создания переднего плана для определения пула переднего плана или сервера Standard Edition для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="598bb-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="598bb-121">Подробности можно найти [в разделе Определение и Настройка внешнего пула и сервера Standard Edition в Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="598bb-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

