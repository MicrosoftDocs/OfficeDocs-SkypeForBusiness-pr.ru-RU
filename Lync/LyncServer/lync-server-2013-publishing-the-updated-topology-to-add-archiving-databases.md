---
title: 'Lync Server 2013: публикация обновленной топологии для добавления архивных баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5834c6c7d0386f7943c523a184ea63f8ba129a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512246"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="e02fe-102">Публикация обновленной топологии для добавления баз данных архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e02fe-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02fe-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e02fe-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e02fe-104">После обновления топологии в построителе топологий необходимо опубликовать топологию в центральном хранилище управления, прежде чем вы сможете настроить и использовать архивацию.</span><span class="sxs-lookup"><span data-stu-id="e02fe-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="e02fe-105">Копии данных, доступные только для чтения, реплицируются на все серверы в топологии, чтобы они были синхронизированы с топологией и другими изменениями конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e02fe-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="e02fe-106">Публикация обновленной топологии</span><span class="sxs-lookup"><span data-stu-id="e02fe-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="e02fe-107">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server Войдите в систему с учетной записью, которая является членом локальной группы "Пользователи" (или учетной записью с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="e02fe-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e02fe-108">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления сервера в топологию, необходимо использовать учетную запись, входящую в группу <STRONG>"Администраторы домена</STRONG> " и группу <STRONG>RTCUniversalServerAdmins</STRONG> . и обладает разрешениями на полный доступ (чтение, запись и изменение) к общему файловому ресурсу, используемому для хранилища файлов Lync Server 2013 (то есть, чтобы построитель топологий мог настроить необходимый избирательный список управления доступом (DACL) или учетную запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="e02fe-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="e02fe-109">Откройте топологию, созданную в предыдущем разделе, с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="e02fe-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="e02fe-110">В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="e02fe-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="e02fe-111">На странице **Публикация топологии** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e02fe-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="e02fe-112">На странице **Создание баз данных** убедитесь, что выбрана база данных, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e02fe-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e02fe-113">Если у вас нет соответствующих разрешений на создание баз данных, можно отменить выбор базы данных, чтобы пользователь с нужными разрешениями создал базу данных.</span><span class="sxs-lookup"><span data-stu-id="e02fe-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="e02fe-114">Для получения дополнительных сведений о необходимых правах и разрешениях администратора ознакомьтесь с <A href="lync-server-2013-deployment-permissions-for-sql-server.md">разрешениями на развертывание для SQL Server в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e02fe-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e02fe-115">С помощью построителя топологий можно устанавливать только базы данных на выделенных серверах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e02fe-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="e02fe-116">Базы данных на серверах SQL Server, размещенные с другими компонентами сервера, должны быть установлены путем запуска локальной программы установки на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="e02fe-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="e02fe-117">На странице **Завершение работы мастера публикации** убедитесь, что топология успешно опубликована, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e02fe-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e02fe-118">После публикации топологии нужно настроить параметры и политики архивации, чтобы получить возможность архивации контента.</span><span class="sxs-lookup"><span data-stu-id="e02fe-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="e02fe-119">Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-support-for-archiving.md">Настройка поддержки архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e02fe-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

