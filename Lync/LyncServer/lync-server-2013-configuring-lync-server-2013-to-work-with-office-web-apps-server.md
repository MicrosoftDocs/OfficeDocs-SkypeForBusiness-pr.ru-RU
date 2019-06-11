---
title: Настройка Lync Server 2013 для работы с сервером Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="aa9ab-102">Настройка Lync Server 2013 для работы с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="aa9ab-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa9ab-103">_**Тема последнего изменения:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="aa9ab-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="aa9ab-104">Прежде чем настраивать Lync Server 2013 для использования сервера Office Web Apps, необходимо развернуть и настроить сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="aa9ab-105">Подробные сведения о том, как установить и настроить один сервер Office Web Apps, а также о том, как установить и настроить сервер Office Web Apps на высоком уровне, можно найти в руководстве по документу, в котором вы можете **Развернуть Office Web Apps Server и Office Web Apps** . официального.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="aa9ab-106">После успешной установки Office Web Apps и правильной настройки веб-фермы необходимо настроить Lync Server для связи с новым сервером; Это можно сделать, добавив URL-адрес обнаружения сервера Office Web Apps в топологию сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="aa9ab-107">Чтобы добавить сервер Office Web Apps в топологию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aa9ab-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="aa9ab-108">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="aa9ab-109">В диалоговом окне **построителя топологий** выберите **Загрузить топологию из существующего развертывания**, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="aa9ab-p103">В диалоговом окне **Сохранить топологию как** введите имя документа топологии (например, **PreWebAppsServerTopology**) в поле **Имя файла**, затем нажмите кнопку **Сохранить**. В случае неполадок с новой топологией в дальнейшем можно будет восстановить сохраненную топологию и повторно опубликовать ее.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="aa9ab-112">В построителе топологии разверните узел **Lync Server 2013**, разверните имя сайта, а затем разверните **Пулы переднего плана Enterprise Edition**, щелкните правой кнопкой мыши имя одного из пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="aa9ab-113">В диалоговом окне **Изменение свойств** на вкладке **Общие** найдите заголовок **Создать связь с сервером Office Web Apps**, затем нажмите кнопку **Создать** (или выберите существующий сервер Office Web Apps в раскрывающемся списке).</span><span class="sxs-lookup"><span data-stu-id="aa9ab-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="aa9ab-114">В диалоговом окне **Определение нового сервера Office Web Apps** введите полное доменное имя (FQDN) сервера Office Web Apps в поле **Полное доменное имя сервера Office Web Apps**; при этом URL-адрес для обнаружения сервера Office Web Apps автоматически вводится в поле **URL-адрес обнаружения сервера Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="aa9ab-115">Если сервер Office Web Apps установлен в локальной сети и в той же сетевой зоне, что и Lync Server 2013, этот вариант не должен быть установлен на **внешний сервер Office Web Apps (например, демилитаризованная зона или Интернет)** .</span><span class="sxs-lookup"><span data-stu-id="aa9ab-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="aa9ab-116">Если сервер Office Web Apps развернут за пределами внутреннего брандмауэра, выберите режим **Сервер Office Web Apps развернут во внешней сети (периметр/Интернет)**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="aa9ab-117">В диалоговом окне **Определение нового сервера Office Web Apps** нажмите кнопку **ОК**, затем нажмите кнопку **ОК** в диалоговом окне **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="aa9ab-118">После этого URL-адрес обнаружения Office Web Apps будет указан как одно из сопоставлений пула.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="aa9ab-119">Затем необходимо повторить этот процесс для каждого пула, который необходимо связать с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="aa9ab-120">После добавления URL-адреса обнаружения в топологию необходимо опубликовать эту обновленную топологию.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="aa9ab-121">Для этого выполните следующие действия в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="aa9ab-122">Щелкните **Действие**, затем **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="aa9ab-123">В мастере публикации топологии на странице **Опубликовать топологию** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="aa9ab-124">На странице **Завершение мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="aa9ab-125">Закройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="aa9ab-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

