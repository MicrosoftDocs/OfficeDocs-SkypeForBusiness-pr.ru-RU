---
title: 'Lync Server 2013: публикация обновленной топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="f69f8-102">Публикация обновленной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f69f8-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f69f8-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f69f8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f69f8-104">После обновления топологии в построителе топологии необходимо опубликовать топологию в хранилище Central Management, прежде чем можно будет настроить и использовать сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="f69f8-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="f69f8-105">Копии данных, доступные только для чтения, реплицируются на все серверы в топологии, чтобы они были синхронизированы с топологией и другими изменениями конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f69f8-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="f69f8-106">Публикация обновленной топологии</span><span class="sxs-lookup"><span data-stu-id="f69f8-106">To publish an updated topology</span></span>

<span data-ttu-id="f69f8-107">Прежде чем публиковать топологию, установите для сервера сохраняемого чата базы данных.</span><span class="sxs-lookup"><span data-stu-id="f69f8-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="f69f8-108">Используйте построитель топологии для установки баз данных, выбрав **действие** и **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="f69f8-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="f69f8-109">На компьютере с Lync Server 2013 или на котором установлены средства администрирования Lync Server, войдите в систему с помощью учетной записи, которая входит в группу **администраторов домена** и **рткуниверсалсерверадминс** . и у него есть разрешения на полный доступ (то есть чтение, запись и изменение) в хранилище файлов, которое будет использоваться для хранения файлов на сервере сохраняемого чата (чтобы Topology Builder мог настроить нужные списки управления доступом на уровне пользователей) или учетную запись с эквивалентными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="f69f8-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="f69f8-110">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="f69f8-110">Start Topology Builder.</span></span> <span data-ttu-id="f69f8-111">Выберите параметр **топология скачивания из существующего развертывания**или **открывайте топологию локального файла** , если вы сохранили его локально.</span><span class="sxs-lookup"><span data-stu-id="f69f8-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="f69f8-112">В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="f69f8-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="f69f8-113">На странице **Публикация топологии** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f69f8-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="f69f8-114">На странице **Работа мастера публикации завершена** убедитесь, что топология успешно опубликована, а затем щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f69f8-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f69f8-115">После публикации топологии необходимо настроить поддержку сервера сохраняемого чата, прежде чем можно будет архивировать содержимое.</span><span class="sxs-lookup"><span data-stu-id="f69f8-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

