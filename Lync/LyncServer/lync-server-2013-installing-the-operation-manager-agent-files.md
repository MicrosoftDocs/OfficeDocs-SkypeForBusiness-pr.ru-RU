---
title: 'Lync Server 2013: Установка файлов агента Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8675e6c75c288e6594e45ecdcc2f65497a047a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="e1971-102">Установка файлов агента Operations Manager в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1971-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1971-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e1971-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e1971-104">Чтобы установить файлы агента Operations Manager на компьютере, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e1971-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="e1971-105">На установочном носителе System Center дважды щелкните **сетупом. exe**.</span><span class="sxs-lookup"><span data-stu-id="e1971-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="e1971-106">В программе System Center Operation Manager нажмите кнопку **установить агент Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="e1971-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="e1971-107">В мастере настройки System Center на странице **Добро пожаловать в мастер настройки System Center Operations Manager** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="e1971-108">На странице **Конечная папка** выберите папку, в которую будут установлены файлы агента Operations Manager, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="e1971-109">На странице **Конфигурация группы управления** выберите **задать сведения о группе управления**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e1971-110">На странице **Конфигурация группы управления** введите имя группы управления Operations Manager в поле **имя группы управления** , а затем введите имя узла сервера Operations Manager (например, ATL-SCOM-001) в \*\* Поле сервер управления\*\* .</span><span class="sxs-lookup"><span data-stu-id="e1971-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="e1971-111">Если вы изменили номер порта, используемый Operations Manager, введите новый номер порта в поле Порт сервера управления.</span><span class="sxs-lookup"><span data-stu-id="e1971-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="e1971-112">В противном случае оставьте значение по умолчанию для порта 5723 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="e1971-113">На странице **учетной записи действия агента** выберите пункт **Локальная система**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="e1971-114">На странице **центра обновления Майкрософт** выберите вариант **я не хочу использовать Microsoft Update**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e1971-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="e1971-115">На странице " **Готово для установки** " нажмите кнопку " **установить**".</span><span class="sxs-lookup"><span data-stu-id="e1971-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="e1971-116">На странице **Завершение работы мастера установки System Center Operations Manager** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e1971-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="e1971-117">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="e1971-117">Click **Exit**.</span></span>

<span data-ttu-id="e1971-118">Если вы используете System Center 2007 R2, вы можете проверить, создан ли агент, нажав кнопку **Пуск**, последовательно выбрав пункты **все программы**, **System Center Operations Manager 2007 R2**и выбрав команду **Shell Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="e1971-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="e1971-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="e1971-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="e1971-120">На экран будет отображен список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="e1971-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="e1971-121">Если вы используете System Center 2012, выполните эту команду из оболочки диспетчера Operations 2012:</span><span class="sxs-lookup"><span data-stu-id="e1971-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

