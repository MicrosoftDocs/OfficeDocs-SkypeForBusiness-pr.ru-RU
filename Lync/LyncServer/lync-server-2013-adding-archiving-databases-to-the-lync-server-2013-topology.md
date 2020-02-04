---
title: 'Lync Server 2013: добавление архивных баз данных в топологию Lync Server 2013'
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
ms.openlocfilehash: 7476107b064b45dbef74b03ff9d54e02fc9eee52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="f30b7-102">Добавление архивных баз данных в топологию Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f30b7-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f30b7-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f30b7-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f30b7-104">Перед настройкой поддержки архивации в развертывании необходимо встроить ее в топологию.</span><span class="sxs-lookup"><span data-stu-id="f30b7-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="f30b7-105">В этой статье объясняется, как с помощью Topology Builder добавить архивацию в существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="f30b7-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f30b7-106">Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013 для всех пользователей в развертывании, не указывайте параметр <STRONG>Архивирование хранилища SQL Server</STRONG> или <STRONG>Используйте сведения о зеркальном ОТОБРАЖЕНии хранилища SQL</STRONG> Server.</span><span class="sxs-lookup"><span data-stu-id="f30b7-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="f30b7-107">Добавление поддержки архивной базы данных в топологию</span><span class="sxs-lookup"><span data-stu-id="f30b7-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="f30b7-108">На компьютере, на котором работает Lync Server 2013 или на котором установлены средства администрирования сервера Lync, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователей).</span><span class="sxs-lookup"><span data-stu-id="f30b7-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f30b7-109">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления сервера в топологию. Вы должны использовать учетную запись, которая входит в группу <STRONG>"Администраторы домена"</STRONG> и группу <STRONG>рткуниверсалсерверадминс</STRONG> , и у нее есть разрешения на полный доступ (например, чтение, запись и изменение) в общей папке, которую вы используете для работы с хранилищем файлов Lync Server 2013 (то есть построителю топологии может настроить требуемый список управления доступом на уровне пользователей (DACL). или учетной записи с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="f30b7-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f30b7-110">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="f30b7-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f30b7-111">В дереве консоли перейдите к пулу переднего плана, на котором вы хотите развернуть архивирование, и щелкните имя пула переднего плана, на котором вы хотите развернуть архивирование.</span><span class="sxs-lookup"><span data-stu-id="f30b7-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="f30b7-112">В меню **Действие** выберите **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="f30b7-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="f30b7-113">В диалоговом окне **Изменение свойств** щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="f30b7-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="f30b7-114">Прокрутите вниз до раздела **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="f30b7-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="f30b7-115">Установите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="f30b7-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="f30b7-116">В разделе **Архивация хранилища SQL Server** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f30b7-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="f30b7-117">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="f30b7-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="f30b7-118">Если все пользователи находятся на сервере Microsoft Exchange Server 2013 или более поздней версии, вы можете архивировать средства связи Lync для всех пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="f30b7-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="f30b7-119">В этом случае вам не нужно настраивать хранилище архивации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f30b7-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="f30b7-120">Чтобы указать новое хранилище SQL Server, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f30b7-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="f30b7-121">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f30b7-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="f30b7-122">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f30b7-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="f30b7-123">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f30b7-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="f30b7-124">Если вы хотите использовать зеркальное отображение хранилища SQL Server, установите флажок **включить зеркальное отображение хранилища SQL**Server, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f30b7-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="f30b7-125">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке " **Архивирование хранилища SQL Server** " выберите имя хранилища SQL Server, которое вы хотите использовать для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="f30b7-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="f30b7-126">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f30b7-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="f30b7-127">В **доменном имени SQL Server**укажите полное доменное имя сервера SQL Server, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f30b7-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="f30b7-128">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f30b7-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="f30b7-129">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f30b7-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f30b7-130">При включении зеркального отображения SQL Server и необходимости включения следящего сервера SQL Server (третий, отдельный экземпляр SQL Server, который может определять работоспособность основного сервера SQL Server и зеркальных экземпляров) установите флажок **использовать следящий сервер зеркального отображения SQL Server, чтобы включить автоматический переход на другой ресурс** , а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f30b7-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="f30b7-131">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новый следящий сервер SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f30b7-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="f30b7-132">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите экземпляр, который будет служить следящим сервером зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="f30b7-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="f30b7-133">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f30b7-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="f30b7-134">Для сохранения конфигурации нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f30b7-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

