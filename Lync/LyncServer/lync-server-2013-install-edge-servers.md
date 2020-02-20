---
title: 'Lync Server 2013: Установка пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="a3b51-102">Установка пограничных серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3b51-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3b51-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a3b51-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a3b51-104">Вы устанавливаете Lync Server 2013 на пограничных серверах с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3b51-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="a3b51-105">Запуская мастер развертывания на каждом пограничном сервере, вы можете выполнить большинство задач, необходимых для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a3b51-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="a3b51-106">Чтобы развернуть Lync Server 2013 на пограничном сервере, необходимо уже запустить построитель топологий, чтобы определить и опубликовать топологию пограничного сервера, а затем экспортировать ее на носитель, доступный с пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a3b51-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="a3b51-107">Дополнительные сведения: [сценарии доступа внешних пользователей в Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) и [их копирования на внешние носители для установки пограничного 2013 сервера](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3b51-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="a3b51-108">После использования мастера развертывания для установки каждого пограничного сервера, установки и назначения необходимых сертификатов и запуска необходимых служб можно выполнить настройку, используя сведения из [настройки поддержки доступа внешних пользователей в Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) , чтобы включить и настроить доступ внешних пользователей, а также сведения о [проверке пограничного развертывания в Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) для проверки установки, включая подключение сервера и клиента.</span><span class="sxs-lookup"><span data-stu-id="a3b51-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="a3b51-109">Установка пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a3b51-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="a3b51-110">Войдите в систему на компьютере, на котором требуется установить пограничный сервер, в качестве члена группы "Локальные администраторы" или с учетной записью с с эквивалентными правами и разрешениями.</span><span class="sxs-lookup"><span data-stu-id="a3b51-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="a3b51-111">Убедитесь, что файл конфигурации топологии, созданный с помощью построителя топологий и затем экспортированный и скопированный на внешний носитель, доступен на пограничном сервере (например, доступ к USB-диску, на который вы скопировали файл конфигурации топологии, или проверьте доступ к сетевой папке, в которую вы скопировали файл).</span><span class="sxs-lookup"><span data-stu-id="a3b51-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="a3b51-112">Запустите мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="a3b51-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3b51-p102">Если отображается сообщение о том, что необходимо установить распространяемый компонент Microsoft Visual C + +, нажмите кнопку <STRONG>Да</STRONG>. В следующем диалоговом окне можно принять значения по умолчанию для параметра <STRONG>Папка установки</STRONG> или нажать кнопку <STRONG>Обзор</STRONG>, чтобы выбрать другое расположение. Затем нажмите кнопку <STRONG>Установить</STRONG>. В следующем диалоговом окне установите флажок <STRONG>Я принимаю условия лицензионного соглашения</STRONG> и нажмите кнопку <STRONG>ОК</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a3b51-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="a3b51-116">В мастере развертывания щелкните **Установить или обновить Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3b51-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="a3b51-117">После того, как мастер определит состояние развертывания (на **Шаге 1. Установка локального хранилища конфигурации**), нажмите кнопку **Выполнить** и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a3b51-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="a3b51-118">В диалоговом окне **Настройка локальной реплики центрального хранилища управления** щелкните **Импортировать из файла (рекомендуется для пограничных серверов)**, перейдите к местоположению экспортированного файла конфигурации топологии, выберите ZIP-файл, нажмите кнопку **Открыть**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a3b51-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a3b51-119">Мастер развертывания прочитает сведения о конфигурации из файла конфигурации и запишет XML-файл конфигурации на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="a3b51-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="a3b51-120">После завершения процесса **выполнения команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a3b51-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="a3b51-121">В мастере развертывания выберите **Шаг 2: Установка или удаление компонентов Lync Server** для установки компонентов lync Server 2013 EDGE, заданных в XML-файле конфигурации, который хранится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a3b51-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="a3b51-122">После завершения установки используйте сведения в разделе [Set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) , чтобы установить и назначить необходимые сертификаты перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="a3b51-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

