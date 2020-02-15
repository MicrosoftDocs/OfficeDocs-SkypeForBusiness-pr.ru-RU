---
title: 'Lync Server 2013: Настройка хранилища файлов DFS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce6be2a3fce1f334e9e4b1d14ea41a3dd57a6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="b44b0-102">Настройка хранилища файлов DFS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b44b0-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b44b0-103">_**Последнее изменение темы:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="b44b0-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="b44b0-104">Lync Server 2013 поддерживает использование файловых ресурсов распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="b44b0-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="b44b0-105">Подробнее о DFS для Windows Server 2008 вы найдете в статье Пошаговое руководство по работе с DFS для Windows Server 2008 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)по адресу. Чтобы использовать DFS, Lync Server 2013 требует наличия следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="b44b0-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="b44b0-106">Пространства имен являются доменными.</span><span class="sxs-lookup"><span data-stu-id="b44b0-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="b44b0-107">Все серверы пространств имен работают под управлением Windows 2008 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b44b0-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="b44b0-108">Для установки Lync Server 2013 необходимо, чтобы разрешения для общей папки разрешают полный доступ к администратору.</span><span class="sxs-lookup"><span data-stu-id="b44b0-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="b44b0-109">В этом случае Lync Server 2013 будет использовать разрешения NTFS для папок списка управления доступом.</span><span class="sxs-lookup"><span data-stu-id="b44b0-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="b44b0-110">Унаследованные разрешения для общих папок DFS не будут использоваться для ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="b44b0-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="b44b0-111">Дополнительные сведения о требованиях к общему файловому ресурсу приведены [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="b44b0-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b44b0-112">Возможно, вы ищете сведения о настройке общего ресурса, не относящегося к DFS.</span><span class="sxs-lookup"><span data-stu-id="b44b0-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="b44b0-113">Если это так, проверьте <A href="lync-server-2013-hardware-setup.md">настройку аппаратного обеспечения для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b44b0-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b44b0-114">Ниже описывается, как правильно настроить разрешения для общих папок с помощью мастера пространств имен DFS (как описано в руководстве по настройке DFS).</span><span class="sxs-lookup"><span data-stu-id="b44b0-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="b44b0-115">Настройка разрешений для общих папок</span><span class="sxs-lookup"><span data-stu-id="b44b0-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="b44b0-116">В меню **Пуск** последовательно выберите пункты **Все программы**, **Администрирование** и **Управление DFS**.</span><span class="sxs-lookup"><span data-stu-id="b44b0-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="b44b0-117">В дереве консоли оснастки "Управление DFS" щелкните правой кнопкой мыши сервер пространства имен (например, filesrv1.contoso.com) и выберите пункт **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="b44b0-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="b44b0-118">Выберите пункт **Разрешения для общей папки**.</span><span class="sxs-lookup"><span data-stu-id="b44b0-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="b44b0-119">Выберите пункт **Использовать пользовательские разрешения**.</span><span class="sxs-lookup"><span data-stu-id="b44b0-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="b44b0-120">Для группы администраторов выберите в разделе **Разрешить** следующие пункты:</span><span class="sxs-lookup"><span data-stu-id="b44b0-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="b44b0-121">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="b44b0-121">**Full Control**</span></span>
    
      - <span data-ttu-id="b44b0-122">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="b44b0-122">**Change**</span></span>
    
      - <span data-ttu-id="b44b0-123">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="b44b0-123">**Read**</span></span>

6.  <span data-ttu-id="b44b0-124">Нажмите кнопку **Применить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b44b0-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

