---
title: Установка основных файлов Lync Server 2013 и базы данных RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc12092e08980fcb1863b18805260ac307cc6d3d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534866"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="cad6b-102">Установка основных файлов Lync Server 2013 и базы данных RTCLocal</span><span class="sxs-lookup"><span data-stu-id="cad6b-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cad6b-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cad6b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cad6b-104">Чтобы установить основные файлы Lync Server 2013 на компьютер, выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="cad6b-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="cad6b-105">База данных RTCLocal устанавливается автоматически при установке файлов основных данных.</span><span class="sxs-lookup"><span data-stu-id="cad6b-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="cad6b-106">Обратите внимание, что не требуется устанавливать SQL Server на узлах-наблюдателях.</span><span class="sxs-lookup"><span data-stu-id="cad6b-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="cad6b-107">Вместо этого экспресс-выпуск SQL Server устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="cad6b-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="cad6b-108">Установка основных файлов Lync Server 2013 и базы данных RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="cad6b-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="cad6b-109">На компьютере узла-наблюдателя в меню **Пуск** щелкните **Все программы**, выберите **Стандартные**, щелкните правой кнопкой мыши **Командная строка**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="cad6b-110">В окне консоли введите следующую команду и нажмите клавишу ВВОД, указав соответствующий путь к файлам установки Lync Server:</span><span class="sxs-lookup"><span data-stu-id="cad6b-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="cad6b-111">Чтобы убедиться, что основные компоненты Lync Server были успешно установлены, нажмите кнопку **Пуск**, выберите **все программы**, **Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="cad6b-112">В консоли управления Lync Server 2013 введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="cad6b-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="cad6b-113">При первом выполнении этой команды данные не возвращаются, так как в качестве узла-наблюдателя не настроек ни один компьютер.</span><span class="sxs-lookup"><span data-stu-id="cad6b-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="cad6b-114">Если команда выполняется без возврата ошибки, можно предположить, что установка Lync Server выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="cad6b-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="cad6b-115">Если компьютер узла-наблюдателя расположен внутри сети периметра, можно выполнить следующую команду, чтобы проверить установку Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="cad6b-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="cad6b-116">Отобразятся данные в следующем виде в соответствии с количеством политик ПИН-кодов, настроенных для организации:</span><span class="sxs-lookup"><span data-stu-id="cad6b-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="cad6b-117">Если отображаются сведения о политиках ПИН-кодов, это означает, что основные компоненты были успешно установлены.</span><span class="sxs-lookup"><span data-stu-id="cad6b-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

