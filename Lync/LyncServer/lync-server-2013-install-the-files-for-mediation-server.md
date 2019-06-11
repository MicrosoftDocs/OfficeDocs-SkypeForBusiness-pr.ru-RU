---
title: 'Lync Server 2013: Установка сервера исправлений для файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="95f57-102">Установка сервера исправлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f57-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f57-103">_**Тема последнего изменения:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="95f57-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="95f57-104">Для успешного выполнения этой процедуры необходимо войти на сервер как минимум с учетной записью локального администратора и пользователя домена, которая является членом группы RTCUniversalReadOnlyAdmins или группы, имеющей более высокие привилегии.</span><span class="sxs-lookup"><span data-stu-id="95f57-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="95f57-105">Выполните действия, описанные в этом разделе, чтобы запустить мастер развертывания Lync Server 2013, чтобы установить сервер для устранения неполадок на компьютере, который был добавлен в пул серверов-исправлений при использовании Topology Builder для определения и публикации пула.</span><span class="sxs-lookup"><span data-stu-id="95f57-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="95f57-106">При установке сервера обновлений файлов вы также установите и назначьте сертификат, необходимый для каждого компьютера в пуле серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="95f57-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="95f57-107">На этом сайте, если вы уже развернули серверы-исправления, выровненные на интерфейсных пулах и серверах Standard Edition, вы можете пропустить этот раздел и, не завершив [настройку каналов в Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="95f57-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95f57-108">В этой статье предполагается, что вы уже определили и опубликовали пул серверов с изолированными исправлениями, как описано в разделе <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Определение сервера-посредника в построителе топологии в Lync server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Server 2013</A> в развертывании и убедитесь, что компьютеры в составе пула сервера ресурсов соответствуют требованиям, описанным в разделе <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">требования к программному обеспечению для корпоративных голосовых документов в Lync Server 2013</A> и <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">требования к безопасности и конфигурации для Корпоративная голосовая связь в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="95f57-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="95f57-109">Установка файлов для автономного пула серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="95f57-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="95f57-110">На установочном носителе щелкните правой кнопкой мыши \<установочный\>**\\\\с\\помощью программы Setup. exe**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="95f57-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="95f57-111">На странице **Папка установки** нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95f57-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="95f57-p102">На странице **Лицензионное соглашение** нажмите кнопку **Принимаю**, а затем нажмите **ОК**. (Требуется для продолжения.)</span><span class="sxs-lookup"><span data-stu-id="95f57-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="95f57-114">На странице **мастера развертывания Lync server 2010** щелкните ссылку **Установка или обновление системы Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="95f57-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="95f57-115">Рядом со строкой **Шаг 1. Установка локального хранилища конфигурации** нажмите кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="95f57-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="95f57-116">На странице **Настройка локальной реплики центрального хранилища управления** примите значение параметра **Извлечь данные непосредственно из центрального хранилища управления** по умолчанию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95f57-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="95f57-117">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95f57-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="95f57-118">Рядом с **шагом 2: Настройка или удаление компонентов Lync Server**нажмите кнопку **выполнить**, а затем — кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95f57-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="95f57-119">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95f57-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="95f57-p103">Нажмите кнопку **Выполнить** рядом со строкой **Шаг 3. Запрос, установка и назначение сертификатов**. Следуйте инструкциям на экране, приняв значения по умолчанию. Для сервера-посредника требуется один сертификат, поэтому вы выполните **шаг 3** дважды: один раз, чтобы издать нужный сертификат, и второй раз, чтобы его назначить.</span><span class="sxs-lookup"><span data-stu-id="95f57-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="95f57-123">После выдачи и корректного назначения сертификата нажмите рядом со строкой **Шаг 4. Запуск служб** кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="95f57-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="95f57-124">После успешного завершения **шага 4** перезапустите сервер и войдите на него как участник группы DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="95f57-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="95f57-125">На компьютере, на котором работает панель управления Lync Server, проверьте на странице **Topology** (топология) панели управления Lync Server, что состояние службы сервера-посредника отображается как зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="95f57-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="95f57-126">If a red X appears instead, select the Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="95f57-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="95f57-127">On the **Action** menu, click **Start All Services**.</span><span class="sxs-lookup"><span data-stu-id="95f57-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="95f57-128">Если вы добавили несколько компьютеров к группе "сервер исправлений", выполните действия, описанные в этой процедуре, на всех остальных компьютерах в пуле сервера исправлений.</span><span class="sxs-lookup"><span data-stu-id="95f57-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="95f57-129">Если вы не хотите устанавливать файлы для сервера исправлений на другие компьютеры, выполните действия, описанные в разделе [Настройка каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md) , чтобы настроить параметры подключения по каналу магистрали между этим пулом сервера исправлений (или всеми исправлениями). Серверы на сайте) и его одноранговый элемент.</span><span class="sxs-lookup"><span data-stu-id="95f57-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95f57-130">См. также</span><span class="sxs-lookup"><span data-stu-id="95f57-130">See Also</span></span>


[<span data-ttu-id="95f57-131">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f57-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

