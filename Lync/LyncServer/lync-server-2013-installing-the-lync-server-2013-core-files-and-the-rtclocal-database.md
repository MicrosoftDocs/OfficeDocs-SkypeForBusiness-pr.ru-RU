---
title: Установка основных файлов Lync Server 2013 и базы данных Ртклокал
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="36529-102">Установка основных файлов Lync Server 2013 и базы данных Ртклокал</span><span class="sxs-lookup"><span data-stu-id="36529-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36529-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="36529-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="36529-104">Чтобы установить основные файлы Lync Server 2013 на компьютере, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="36529-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="36529-105">База данных Ртклокал устанавливается автоматически при установке основных файлов.</span><span class="sxs-lookup"><span data-stu-id="36529-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="36529-106">Обратите внимание, что вам не нужно устанавливать SQL Server на узлах наблюдения.</span><span class="sxs-lookup"><span data-stu-id="36529-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="36529-107">Вместо этого SQL Server Express устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="36529-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="36529-108">Чтобы установить основные файлы Lync Server 2013 и базу данных Ртклокал, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="36529-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="36529-109">На компьютере с узлом-наблюдателем нажмите **кнопку Пуск**, **выберите все программы**, затем **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="36529-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="36529-110">В окне консоли введите указанную ниже команду и нажмите клавишу ВВОД, указав соответствующий путь к файлам установки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36529-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="36529-111">Чтобы убедиться в том, что основные компоненты Lync Server были успешно установлены, нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="36529-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="36529-112">В командной консоли Lync Server 2013 введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="36529-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="36529-113">При первом запуске этой команды данные не возвращаются, так как вы еще не настроили ни один из узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="36529-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="36529-114">Если команда выполняется без возврата ошибки, вы можете предположить, что настройка сервера Lync Server выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="36529-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="36529-115">Если ваш компьютер-наблюдатель находится внутри сети периметра, вы можете выполнить следующую команду для проверки установки Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="36529-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="36529-116">В зависимости от количества политик, настроенных для использования в вашей организации, вам будут выводиться такие сведения, как, например, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="36529-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="36529-117">Если вы видите сведения о политиках PIN-кода, это означает, что вы успешно установили основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="36529-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

