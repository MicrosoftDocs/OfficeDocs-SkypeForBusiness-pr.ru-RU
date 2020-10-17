---
title: 'Lync Server 2013: Настройка хранилища файлов DFS'
description: 'Lync Server 2013: Настройка хранилища файлов DFS.'
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
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564385"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="ed7f6-103">Настройка хранилища файлов DFS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7f6-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7f6-104">_**Последнее изменение темы:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="ed7f6-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="ed7f6-105">Lync Server 2013 поддерживает использование файловых ресурсов распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="ed7f6-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="ed7f6-106">Подробнее о DFS для Windows Server 2008 вы найдете в статье Пошаговое руководство по работе с DFS для Windows Server 2008 по адресу [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Чтобы использовать DFS, Lync Server 2013 требует наличия следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="ed7f6-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="ed7f6-107">Пространства имен являются доменными.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="ed7f6-108">Все серверы пространств имен работают под управлением Windows 2008 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="ed7f6-109">Для установки Lync Server 2013 необходимо, чтобы разрешения для общей папки разрешают полный доступ к администратору.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="ed7f6-110">В этом случае Lync Server 2013 будет использовать разрешения NTFS для папок списка управления доступом.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="ed7f6-111">Унаследованные разрешения для общих папок DFS не будут использоваться для ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="ed7f6-112">Дополнительные сведения о требованиях к общему файловому ресурсу приведены [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed7f6-113">Возможно, вы ищете сведения о настройке общего ресурса, не относящегося к DFS.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="ed7f6-114">Если это так, проверьте <A href="lync-server-2013-hardware-setup.md">настройку аппаратного обеспечения для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ed7f6-115">Ниже описывается, как правильно настроить разрешения для общих папок с помощью мастера пространств имен DFS (как описано в руководстве по настройке DFS).</span><span class="sxs-lookup"><span data-stu-id="ed7f6-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="ed7f6-116">Настройка разрешений для общих папок</span><span class="sxs-lookup"><span data-stu-id="ed7f6-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="ed7f6-117">В меню **Пуск** последовательно выберите пункты **Все программы**, **Администрирование** и **Управление DFS**.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="ed7f6-118">В дереве консоли оснастки "Управление DFS" щелкните правой кнопкой мыши сервер пространства имен (например, filesrv1.contoso.com) и выберите пункт **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="ed7f6-119">Выберите пункт **Разрешения для общей папки**.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="ed7f6-120">Выберите пункт **Использовать пользовательские разрешения**.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="ed7f6-121">Для группы администраторов выберите в разделе **Разрешить** следующие пункты:</span><span class="sxs-lookup"><span data-stu-id="ed7f6-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="ed7f6-122">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="ed7f6-122">**Full Control**</span></span>
    
      - <span data-ttu-id="ed7f6-123">**Change**</span><span class="sxs-lookup"><span data-stu-id="ed7f6-123">**Change**</span></span>
    
      - <span data-ttu-id="ed7f6-124">**Read**</span><span class="sxs-lookup"><span data-stu-id="ed7f6-124">**Read**</span></span>

6.  <span data-ttu-id="ed7f6-125">Нажмите кнопку **Применить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

