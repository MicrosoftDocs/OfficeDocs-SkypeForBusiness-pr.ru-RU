---
title: 'Lync Server 2013: изменение параметров базы данных для архивации'
description: 'Lync Server 2013: изменение параметров базы данных для архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543585"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="c227b-103">Изменение параметров базы данных для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c227b-103">Changing Archiving database options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c227b-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c227b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c227b-105">При развертывании архивации с использованием хранилища SQL Server для архивации любых пользователей можно внести следующие изменения в хранилище базы данных:</span><span class="sxs-lookup"><span data-stu-id="c227b-105">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="c227b-106">Используйте другую базу данных SQL Server для архивации данных.</span><span class="sxs-lookup"><span data-stu-id="c227b-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="c227b-107">Сюда входят основная база данных архивации и любая база данных, используемая для зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c227b-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="c227b-108">Переключитесь на Microsoft Exchange Integration для хранения архивных данных и файлов на серверах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c227b-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="c227b-109">Если все пользователи размещены на серверах Exchange 2013 и вы хотите использовать хранилище Microsoft Exchange для всех пользователей в развертывании, необходимо удалить базы данных хранилища SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="c227b-109">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="c227b-110">Чтобы внести какие – либо из этих изменений, необходимо запустить построитель топологий, внести изменения и затем опубликовать топологию еще раз.</span><span class="sxs-lookup"><span data-stu-id="c227b-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="c227b-111">Для этого можно использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="c227b-111">You can use Topology Builder to do this.</span></span> <span data-ttu-id="c227b-112">Не указывайте параметр **Архивация хранилища SQL Server** или включите сведения о **зеркальном отображении хранилища SQL Server** , если пользователи Lync не размещены на серверах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c227b-112">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="c227b-113">Изменение базы данных архивирования</span><span class="sxs-lookup"><span data-stu-id="c227b-113">To change your archiving database option</span></span>

1.  <span data-ttu-id="c227b-114">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server Войдите в систему с помощью учетной записи, которая является членом локальной группы "Пользователи" (или учетной записью с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="c227b-114">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c227b-115">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления компонента в топологию, необходимо использовать учетную запись, которая является членом группы <STRONG>администраторов домена</STRONG> и группы <STRONG>RTCUniversalServerAdmins</STRONG> . и обладает разрешениями на полный доступ (чтение, запись и изменение) к общему файловому ресурсу, используемому для хранилища файлов Lync Server 2013 (то есть, чтобы построитель топологий мог настроить необходимые списки управления доступом на уровне пользователей (DACL) или учетную запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="c227b-115">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="c227b-116">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="c227b-116">Start Topology Builder.</span></span>

3.  <span data-ttu-id="c227b-117">В дереве консоли перейдите к интерфейсному пулу, в котором развернута служба архивирования, и затем щелкните название пула, где нужно изменить параметры базы данных.</span><span class="sxs-lookup"><span data-stu-id="c227b-117">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="c227b-118">В меню **Действие** выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c227b-118">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="c227b-119">В окне **Изменение свойств** щелкните **Общее**.</span><span class="sxs-lookup"><span data-stu-id="c227b-119">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="c227b-120">Прокрутите вниз до **Архивирование**.</span><span class="sxs-lookup"><span data-stu-id="c227b-120">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="c227b-121">В **Архивирование**, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c227b-121">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="c227b-122">Чтобы сменить хранилище SQL Server в **Архивное хранилище SQL Server**, в раскрывающемся списке сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c227b-122">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="c227b-123">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="c227b-123">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="c227b-124">Чтобы указать новое хранилище SQL Server нажмите **Создать** и затем в окне **Определение новое хранилище SQL Server** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c227b-124">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="c227b-125">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="c227b-125">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="c227b-126">Чтобы указать новое хранилище SQL Server, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c227b-126">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="c227b-127">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера, на котором требуется создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c227b-127">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="c227b-128">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите **Именованный экземпляр**, и затем укажите нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c227b-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="c227b-129">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="c227b-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="c227b-130">Чтобы добавить хранилище SQL Server для зеркалирования или изменить хранилище для зеркалирования установите флажок **Включить зеркалирование хранилища SQL Server**, и затем сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c227b-130">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="c227b-131">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке **зеркало хранилища SQL Server для архивации** щелкните имя хранилища SQL Server, которое требуется использовать для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="c227b-131">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="c227b-132">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c227b-132">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="c227b-133">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера SQL Server, на котором нужно создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c227b-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="c227b-134">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите нажмите **Именованный экземпляр**, и затем укажите нужный.</span><span class="sxs-lookup"><span data-stu-id="c227b-134">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="c227b-135">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="c227b-135">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="c227b-136">Если вы включите зеркальное отображение SQL Server и хотите добавить или изменить следящий сервер SQL Server (третий, отдельный экземпляр SQL Server, который может обнаружить работоспособность основного сервера SQL Server и зеркальных экземпляров), установите флажок **использовать следящий сервер зеркального отображения SQL Server для включения автоматического перехода на другой ресурс** и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c227b-136">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="c227b-137">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера, на котором необходимо создать новый следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c227b-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="c227b-138">Либо нажмите **Экземпляр по умолчанию**, либо **Именованный экземпляр**, чтобы указать нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c227b-138">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="c227b-139">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="c227b-139">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="c227b-140">Чтобы переключиться на интеграцию Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013 (если все пользователи в развертывании размещены на серверах Exchange 2013), удалите все данные для архивных баз данных.</span><span class="sxs-lookup"><span data-stu-id="c227b-140">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c227b-141">Если у вас есть пользователи Lync, которые не размещены на серверах Exchange 2013, не удаляйте данные из хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c227b-141">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="c227b-142">Чтобы сохранить конфигурацию, нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c227b-142">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c227b-143">Изменения, внесенные в построителе топологий, вступают в силу только после публикации новой топологии.</span><span class="sxs-lookup"><span data-stu-id="c227b-143">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="c227b-144">Дополнительные сведения см в статье <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Публикация обновленной топологии для добавления баз данных архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c227b-144">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

