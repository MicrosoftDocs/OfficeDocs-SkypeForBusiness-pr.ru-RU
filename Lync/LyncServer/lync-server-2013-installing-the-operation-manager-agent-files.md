---
title: 'Lync Server 2013: Установка файлов агента Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48624e3f93ebb133743680a01399444137385a0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="fa7a9-102">Установка файлов агента Operations Manager в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa7a9-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa7a9-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fa7a9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fa7a9-104">Чтобы установить на компьютер файлы агента Operations Manager, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="fa7a9-105">В установочном носителе System Center дважды щелкните программу **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fa7a9-106">В окне установки System Center Operations Manager выберите **Установить агент Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="fa7a9-107">На странице **приветствия** мастера установки System Center нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="fa7a9-108">На странице указания **папки назначения** выберите папку, в которую должны устанавливаться файлы агента Operations Manager и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="fa7a9-109">На странице **Конфигурация группы управления** выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="fa7a9-p101">На странице **Конфигурация группы управления** в поле **Имя группы управления** введите имя группы управления Operations Manager, а в поле **Сервер управления** введите имя узла сервера Operations Manager (например, atl-scom-001). Если номер порта, используемый Operations Manager, был изменен, то в поле "Порт сервера управления" укажите этот новый номер. Если номер порта не изменялся, то оставьте значение по умолчанию 5723 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-p101">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box. If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box. Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="fa7a9-113">На странице **Учетная запись действий агента** выберите **Local System** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="fa7a9-114">На странице **Центр обновления Майкрософт** выберите **Не использовать Центр обновления Майкрософт** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="fa7a9-115">На странице **Все готово для установки** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="fa7a9-116">На странице **Завершение работы мастера установки System Center Operations Manager** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="fa7a9-117">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-117">Click **Exit**.</span></span>

<span data-ttu-id="fa7a9-118">Если вы используете System Center 2007 R2, то можно проверить, создан ли агент, нажав кнопку **Пуск** и последовательно выбрав пункты **Программы**, **System Center Operations Manager 2007 R2** и **Оболочка Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="fa7a9-119">В командной консоли Operations Manager введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="fa7a9-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="fa7a9-120">На экране должен появиться список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fa7a9-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="fa7a9-121">Если вы используете System Center 2012, то выполните в оболочке Operations 2012 Manager Shell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fa7a9-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

