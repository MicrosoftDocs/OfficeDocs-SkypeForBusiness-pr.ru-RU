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
ms.openlocfilehash: 589398c97a17f41f38394d5d3a57da4d3fec14ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="98d63-102">Публикация обновленной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98d63-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98d63-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="98d63-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="98d63-104">После обновления топологии в построителе топологий необходимо опубликовать топологию в центральном хранилище управления, прежде чем можно будет настроить и использовать сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="98d63-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="98d63-105">Доступные только для чтения копии данных реплицируются на все серверы в топологии, чтобы обеспечивать синхронизацию всех серверов для внесения изменений топологии и других изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="98d63-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="98d63-106">Публикация обновленной топологии</span><span class="sxs-lookup"><span data-stu-id="98d63-106">To publish an updated topology</span></span>

<span data-ttu-id="98d63-107">Перед публикацией топологии Установите базы данных для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="98d63-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="98d63-108">Используйте построитель топологий для установки баз данных, выбрав **действие** и **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="98d63-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="98d63-109">Выполните вход с учетной записью, которая является членом группы **администраторов домена** и группы **RTCUniversalServerAdmins** на компьютере, на котором работает Lync Server 2013 или на котором установлены средства администрирования Lync Server. и обладает разрешениями на полный доступ (чтение, запись и изменение) в хранилище файлов, которое будет использоваться для хранилища файлов сервера сохраняемого чата (чтобы построитель топологий мог настроить необходимые избирательные списки управления доступом (DACL)) или учетную запись с эквивалентными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="98d63-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="98d63-110">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="98d63-110">Start Topology Builder.</span></span> <span data-ttu-id="98d63-111">Выберите пункт **Загрузить топологию из существующего развертывания** или **Открыть топологию из локального файла**, если она сохранена локально.</span><span class="sxs-lookup"><span data-stu-id="98d63-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="98d63-112">В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите команду **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="98d63-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="98d63-113">На странице **Публикация топологии** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98d63-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="98d63-114">На странице **Завершение мастера публикации** убедитесь, что топология была успешно опубликована, а затем щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="98d63-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="98d63-115">После публикации топологии необходимо настроить поддержку сервера сохраняемого чата, прежде чем можно будет архивировать любое содержимое.</span><span class="sxs-lookup"><span data-stu-id="98d63-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

