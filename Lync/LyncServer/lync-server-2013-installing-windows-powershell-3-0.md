---
title: 'Lync Server 2013: установка Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="fd411-102">Установка Windows PowerShell 3.0 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd411-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd411-103">_**Тема последнего изменения:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="fd411-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="fd411-104">Для успешного развертывания Lync Server 2013 вам потребуется Windows PowerShell 3,0 на всех компьютерах, входящих в вашу топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd411-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="fd411-105">Теперь для систем под управлением Windows Server 2012 или Windows Server 2012 R2 вам не нужно ничего делать, и можно перейти к следующему этапу развертывания, так как PowerShell 3,0 входит в эти операционные системы.</span><span class="sxs-lookup"><span data-stu-id="fd411-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd411-106">Но для систем под управлением Windows Server 2008 R2 SP1 вам потребуется установить PowerShell 3,0 как необходимый компонент, прежде чем устанавливать Lync Server 2013 или не будет работать.</span><span class="sxs-lookup"><span data-stu-id="fd411-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="fd411-107">Чтобы установить PowerShell 3,0, ознакомьтесь со сведениями о <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">платформе Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="fd411-107">To install PowerShell 3.0, see <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="fd411-108">Это прямая ссылка на страницу загрузки PowerShell 3,0, а также сведения об ее успешном установке.</span><span class="sxs-lookup"><span data-stu-id="fd411-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="fd411-109">После того как вы закончите установку или хотите убедиться, что перед тем как продолжить развертывание Lync Server, убедитесь, что приложение PowerShell 3,0 находится на сервере, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="fd411-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="fd411-110">На сервере, который вы хотите проверить, нажмите **кнопку Пуск**, **выберите все программы**, затем **стандартные**, выберите **Windows PowerShell**и щелкните **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fd411-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="fd411-111">В командной строке консоли Windows PowerShell введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="fd411-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="fd411-112">Если вы установили Windows PowerShell 3,0, отобразится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="fd411-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

