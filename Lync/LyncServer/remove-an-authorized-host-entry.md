---
title: Удаление авторизованной записи узла
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849617676305cc2d7308c0c8b1a48bef327f3c87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="6d90a-102">Удаление авторизованной записи узла</span><span class="sxs-lookup"><span data-stu-id="6d90a-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d90a-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6d90a-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6d90a-104">В этой статье описано, как удалить устаревшую авторизованную запись узла (которая называется *надежной записью приложения* в Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="6d90a-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="6d90a-105">Вы должны удалить существующие авторизованные записи узла для всех шлюзов SIP/КСТА в Office Communications Server 2007 R2, когда вы перенесете управление удаленным звонком в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d90a-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="6d90a-106">Для удаления существующих авторизованных записей узла необходимо использовать средства администрирования, входящие в состав Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6d90a-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="6d90a-107">Удаление авторизованной записи узла в развертывании Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6d90a-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="6d90a-108">Откройте консоль администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6d90a-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="6d90a-109">Разверните дерево и щелкните правой кнопкой мыши пул, в котором был создан авторизованный узел.</span><span class="sxs-lookup"><span data-stu-id="6d90a-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="6d90a-110">Нажмите кнопку **Свойства**, а затем — **Свойства Front End**.</span><span class="sxs-lookup"><span data-stu-id="6d90a-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="6d90a-111">Откройте вкладку **авторизация узла** .</span><span class="sxs-lookup"><span data-stu-id="6d90a-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="6d90a-112">Выберите сервер, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6d90a-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="6d90a-113">В окне " **Свойства**" нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6d90a-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

