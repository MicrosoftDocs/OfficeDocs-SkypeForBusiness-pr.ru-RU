---
title: Настройка Lync Server 2013 для работы с сервером Office Web Apps
description: Настройка Lync Server 2013 для работы с сервером Office Web Apps.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e53500e0ad272c81340c25946f5b7f8e72a121
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570875"
---
# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="1f4ff-103">Настройка Lync Server 2013 для работы с сервером Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="1f4ff-103">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f4ff-104">_**Последнее изменение темы:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="1f4ff-104">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="1f4ff-105">Перед настройкой Lync Server 2013 для использования сервера Office Web Apps необходимо развернуть и настроить сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-105">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="1f4ff-106">Сведения о том, как установить и настроить один сервер Office Web Apps, а также об установке и настройке фермы серверов Office Web Apps для обеспечения высокой доступности, можно найти в руководстве по документу, в котором описано **развертывание Office Web Apps Server и Office Web Apps** .</span><span class="sxs-lookup"><span data-stu-id="1f4ff-106">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="1f4ff-107">После успешной установки Office Web Apps и правильной настройки веб-фермы необходимо настроить Lync Server для подключения к новому серверу; для этого необходимо добавить в топологию Lync Server URL-адрес обнаружения сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-107">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="1f4ff-108">Чтобы добавить сервер Office Web Apps в топологию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1f4ff-108">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="1f4ff-109">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1f4ff-110">В диалоговом окне **Построитель топологии** выберите **Загрузить топологию из существующего развертывания**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="1f4ff-p103">В диалоговом окне **Сохранить топологию как** введите имя документа топологии (например, **PreWebAppsServerTopology**) в поле **Имя файла**, а затем щелкните **Сохранить**. Затем можно будет восстановить и повторно опубликовать эту топологию в случае возникновения проблем с новой топологией.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="1f4ff-113">В построителе топологий разверните узел **Lync Server 2013**, разверните имя сайта, разверните **Пулы переднего плана Enterprise Edition**, щелкните правой кнопкой мыши имя одного из пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-113">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="1f4ff-114">В диалоговом окне **Изменить свойства** на вкладке **Общие** найдите заголовок **Связать сервер Office Web Apps**, а затем щелкните **Создать** (или выберите существующий сервер Office Web Apps в раскрывающемся списке).</span><span class="sxs-lookup"><span data-stu-id="1f4ff-114">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="1f4ff-115">В диалоговом окне **Указать новый сервер Office Web Apps** введите полное доменное имя (FQDN) сервера Office Web Apps в поле **Полное доменное имя сервера Office Web Apps**; при этом URL-адрес обнаружения сервера Office Web Apps должен автоматически отобразиться в поле **URL-адрес обнаружения сервера Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-115">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="1f4ff-116">Если сервер Office Web Apps установлен локально и в той же зоне сети, что и Lync Server 2013, то параметр **сервер Office Web Apps развернут во внешней сети (периметр/Интернет)** не должен быть выбран.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-116">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="1f4ff-117">Если сервер Office Web Apps развернут за пределами внутреннего брандмауэра, выберите параметр **Сервер Office Web Apps развернут во внешней сети (то есть в периметре/Интернете)**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-117">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="1f4ff-p104">В диалоговом окне **Указать новый сервер Office Web Apps** щелкните **ОК**, а затем щелкните **ОК** в диалоговом окне **Изменить свойства**. URL-адрес обнаружения сервера Office Web Apps будет отображаться как одна из связей пула.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="1f4ff-120">Затем необходимо повторить этот процесс для каждого пула, который необходимо связать с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-120">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="1f4ff-p105">После добавления URL-адреса обнаружения в топологию необходимо затем опубликовать эту обновленную топологию. Для этого выполните следующие действия в построителе топологии:</span><span class="sxs-lookup"><span data-stu-id="1f4ff-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="1f4ff-123">Щелкните **Действие**, а затем щелкните **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-123">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="1f4ff-124">В мастере публикации топологии на странице **Опубликовать топологию** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-124">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="1f4ff-125">На странице **Завершение мастера публикации** щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="1f4ff-126">Закройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="1f4ff-126">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

