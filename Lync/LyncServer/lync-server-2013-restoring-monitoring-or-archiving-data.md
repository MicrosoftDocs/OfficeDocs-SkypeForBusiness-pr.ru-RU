---
title: 'Lync Server 2013: восстановление данных мониторинга или архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8840869e972f0c178360b0b50644d352b8db85df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="3236d-102">Восстановление данных мониторинга или архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3236d-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3236d-103">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="3236d-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="3236d-104">Восстановление данных мониторинга и архивации не требуется для того, чтобы сделать Lync Server запущенным после сбоя.</span><span class="sxs-lookup"><span data-stu-id="3236d-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="3236d-105">Тем не менее, если данные мониторинга и архивации важны для вашей организации, необходимо восстановить данные после повторного создания баз данных.</span><span class="sxs-lookup"><span data-stu-id="3236d-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="3236d-106">В следующей процедуре описывается, как использовать SQL Server Management Studio для восстановления данных архивации или мониторинга.</span><span class="sxs-lookup"><span data-stu-id="3236d-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="3236d-107">Восстановление данных мониторинга или архивации из файла резервной копии</span><span class="sxs-lookup"><span data-stu-id="3236d-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="3236d-108">Выполните вход на сервер, который вы восстанавливаете в качестве члена группы "Администраторы" на локальном компьютере или в группе с эквивалентными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="3236d-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="3236d-109">Откройте SQL Server Management Studio: нажмите кнопку **Пуск**, **выберите все программы**, **Microsoft SQL Server 2012** или **Microsoft SQL Server 2008 R2**, а затем щелкните **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="3236d-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="3236d-110">В разделе **Подключение к серверу**подключитесь к экземпляру SQL Server, указав по крайней мере имя сервера и сведения о проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="3236d-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="3236d-111">В **обозревателе объектов**щелкните правой кнопкой мыши **базы данных**и выберите команду **восстановить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="3236d-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="3236d-112">В разделе **Выбор страницы**щелкните **Общие**, а затем в поле **база данных** выберите имя базы данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3236d-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="3236d-113">Для базы данных архивации выберите **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="3236d-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="3236d-114">Для базы данных регистрации вызовов (CDR) выберите **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="3236d-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="3236d-115">Для базы данных качества взаимодействия (QoE) выберите **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="3236d-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="3236d-116">Щелкните **с устройства**.</span><span class="sxs-lookup"><span data-stu-id="3236d-116">Click **From device**.</span></span>

7.  <span data-ttu-id="3236d-117">В списке **Выберите резервные наборы данных для восстановления**выберите файл резервной копии и нажмите кнопку **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="3236d-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="3236d-118">В разделе **Выбор страницы**щелкните **Параметры**, убедитесь, что путь к файлу данных и путь к журналу находятся в правильной папке, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3236d-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="3236d-119">Проверка правильности списков управления доступом (ACL)</span><span class="sxs-lookup"><span data-stu-id="3236d-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="3236d-120">Разверните **узел базы данных, разверните**базу данных архивации или мониторинга, разверните узел **Безопасность**, а затем разверните узел **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3236d-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="3236d-121">Убедитесь, что группа домена RTCComponentUniversalServices существует в качестве пользователя.</span><span class="sxs-lookup"><span data-stu-id="3236d-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="3236d-122">Если RTCComponentUniversalServices не существует в разделе **Пользователи**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3236d-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="3236d-123">Щелкните правой кнопкой мыши узел **Пользователи** и выберите пункт **Новый пользователь**.</span><span class="sxs-lookup"><span data-stu-id="3236d-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="3236d-124">В поле **имя входа**введите недостающее имя группы RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="3236d-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="3236d-125">В разделе **членство в роли базы данных**выберите разрешение **serverRole** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3236d-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3236d-126">Перезапускать службу архивирования и мониторинга не требуется.</span><span class="sxs-lookup"><span data-stu-id="3236d-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

