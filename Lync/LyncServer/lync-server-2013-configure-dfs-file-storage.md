---
title: 'Lync Server 2013: настройка хранилища файлов'
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
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="2412e-102">Настройка хранилища файлов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2412e-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2412e-103">_**Тема последнего изменения:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="2412e-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="2412e-104">Lync Server 2013 поддерживает использование общих файловых ресурсов в распределенной файловой системе (DFS).</span><span class="sxs-lookup"><span data-stu-id="2412e-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="2412e-105">Подробные сведения о DFS для Windows Server 2008 можно найти в пошаговом руководстве по DFS для Windows Server 2008 по адресу [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835). Для использования DFS сервер Lync Server 2013 должен выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2412e-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="2412e-106">Пространства имен основываются на доменах</span><span class="sxs-lookup"><span data-stu-id="2412e-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="2412e-107">На всех серверах пространства имен установлен минимум Windows 2008</span><span class="sxs-lookup"><span data-stu-id="2412e-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="2412e-108">Для установки Lync Server 2013 необходимо, чтобы разрешение на доступ к общей папке было разрешено администратору.</span><span class="sxs-lookup"><span data-stu-id="2412e-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="2412e-109">В этом случае Lync Server 2013 будет использовать разрешения на доступ к файлам NTFS для папок ACL.</span><span class="sxs-lookup"><span data-stu-id="2412e-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="2412e-110">Унаследованные разрешения для общего доступа к DFS не будут использоваться для ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="2412e-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="2412e-111">Дополнительные сведения о требованиях к общему доступу можно найти [в разделе Поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="2412e-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2412e-112">Возможно, вы ищете информацию о настройке общего доступа к сети, не относящейся к DFS.</span><span class="sxs-lookup"><span data-stu-id="2412e-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="2412e-113">Если это так, изучите <A href="lync-server-2013-hardware-setup.md">настройку оборудования для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2412e-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2412e-114">Ниже описано, как правильно настроить разрешения на доступ к общей папке с помощью мастера пространства имен DFS (как описано в руководстве по настройке DFS).</span><span class="sxs-lookup"><span data-stu-id="2412e-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="2412e-115">Настройка разрешений для общей папки</span><span class="sxs-lookup"><span data-stu-id="2412e-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="2412e-116">Нажмите кнопку **Пуск**, наведите указатель на пункт **все программы**, выберите **Администрирование**, а затем — **Управление DFS**.</span><span class="sxs-lookup"><span data-stu-id="2412e-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="2412e-117">В дереве консоли оснастки управления DFS щелкните правой кнопкой мыши сервер пространства имен (например, filesrv1.contoso.com), а затем выберите команду **изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="2412e-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="2412e-118">Выберите **разрешения для общей папки**.</span><span class="sxs-lookup"><span data-stu-id="2412e-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="2412e-119">Выберите **использовать пользовательские разрешения**.</span><span class="sxs-lookup"><span data-stu-id="2412e-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="2412e-120">Для группы администраторов выберите в разделе **разрешено**следующее:</span><span class="sxs-lookup"><span data-stu-id="2412e-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="2412e-121">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="2412e-121">**Full Control**</span></span>
    
      - <span data-ttu-id="2412e-122">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="2412e-122">**Change**</span></span>
    
      - <span data-ttu-id="2412e-123">**Читаются**</span><span class="sxs-lookup"><span data-stu-id="2412e-123">**Read**</span></span>

6.  <span data-ttu-id="2412e-124">Нажмите кнопку **Применить**, а затем — кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2412e-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

