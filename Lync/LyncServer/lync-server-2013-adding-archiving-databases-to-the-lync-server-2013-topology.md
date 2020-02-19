---
title: 'Lync Server 2013: Добавление баз данных архивации в топологию Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bed8e9fa8b15bd4e9e7fb1f72b102ed223edd9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="f3e14-102">Добавление баз данных архивации в топологию Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3e14-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3e14-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f3e14-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f3e14-104">Перед настройкой развертывания для поддержки архивации необходимо включить архивацию в топологию.</span><span class="sxs-lookup"><span data-stu-id="f3e14-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="f3e14-105">Сведения, приведенные в этом разделе, поясняют, как использовать построитель топологий для добавления архивации в существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="f3e14-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3e14-106">Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013 для всех пользователей в развертывании, не указывайте параметр <STRONG>Архивация хранилища SQL Server</STRONG> или <STRONG>использование данных зеркального отображения хранилища SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f3e14-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="f3e14-107">Добавление поддержки архивной базы данных в топологию</span><span class="sxs-lookup"><span data-stu-id="f3e14-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="f3e14-108">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server Войдите в систему с помощью учетной записи, которая является членом локальной группы "Пользователи" (или учетной записью с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="f3e14-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3e14-109">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления сервера в топологию, необходимо использовать учетную запись, которая является членом группы <STRONG>администраторов домена</STRONG> и группы <STRONG>RTCUniversalServerAdmins</STRONG> , и иметь разрешения на полный доступ (чтение, запись и изменение) к общему файловому ресурсу, используемому для хранилища файлов Lync Server 2013 (то есть, чтобы построитель топологии мог настроить необходимый избирательный список управления доступом (DACL) или учетная запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="f3e14-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f3e14-110">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f3e14-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f3e14-111">В дереве консоли перейдите к интерфейсному пулу, в котором требуется развернуть архивацию, а затем щелкните имя пула переднего плана, в котором требуется развернуть архивацию.</span><span class="sxs-lookup"><span data-stu-id="f3e14-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="f3e14-112">В меню **Действие** выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="f3e14-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="f3e14-113">В окне **Изменение свойств** щелкните **Общее**.</span><span class="sxs-lookup"><span data-stu-id="f3e14-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="f3e14-114">Прокрутите вниз до **Архивирование**.</span><span class="sxs-lookup"><span data-stu-id="f3e14-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="f3e14-115">Установите флажок **Архивация** .</span><span class="sxs-lookup"><span data-stu-id="f3e14-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="f3e14-116">В разделе **Архивация хранилища SQL Server** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f3e14-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="f3e14-117">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="f3e14-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="f3e14-118">Если все пользователи размещены на сервере Microsoft Exchange Server 2013 или более поздней версии, вы можете архивировать средства связи Lync для всех пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="f3e14-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="f3e14-119">В этом случае вам не нужно настраивать хранилище архивации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3e14-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="f3e14-120">Чтобы указать новое хранилище SQL Server, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f3e14-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="f3e14-121">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера, на котором требуется создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3e14-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="f3e14-122">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите **Именованный экземпляр**, и затем укажите нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f3e14-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="f3e14-123">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f3e14-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="f3e14-124">Если вы хотите использовать зеркальное отображение хранилища SQL Server, выберите **включить зеркальное отображение хранилища SQL**Server, а затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f3e14-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="f3e14-125">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке **зеркало хранилища SQL Server для архивации** щелкните имя хранилища SQL Server, которое требуется использовать для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="f3e14-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="f3e14-126">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f3e14-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="f3e14-127">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера SQL Server, на котором нужно создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3e14-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="f3e14-128">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите нажмите **Именованный экземпляр**, и затем укажите нужный.</span><span class="sxs-lookup"><span data-stu-id="f3e14-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="f3e14-129">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f3e14-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f3e14-130">Если включено зеркальное отображение SQL Server и вы хотите включить следящий сервер SQL Server (третий, отдельный экземпляр SQL Server, который может обнаружить работоспособность основного сервера SQL Server и зеркальных экземпляров), установите флажок **использовать следящий сервер зеркального отображения SQL Server для включения автоматического перехода на другой ресурс** , а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f3e14-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="f3e14-131">В поле **полное доменное имя SQL**Server укажите полное доменное имя сервера, на котором необходимо создать новый следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3e14-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="f3e14-132">Либо нажмите **Экземпляр по умолчанию**, либо **Именованный экземпляр**, чтобы указать нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f3e14-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="f3e14-133">Если указанный экземпляр SQL Server находится в отношении зеркального отображения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f3e14-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="f3e14-134">Чтобы сохранить конфигурацию, нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3e14-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

