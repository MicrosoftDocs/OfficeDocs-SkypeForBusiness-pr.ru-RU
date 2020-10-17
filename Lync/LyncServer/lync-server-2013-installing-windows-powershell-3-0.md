---
title: 'Lync Server 2013: Установка Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de45679983221d80171dde8dd37397a8b3a965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534786"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="a09f7-102">Установка Windows PowerShell 3,0 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09f7-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a09f7-103">_**Последнее изменение темы:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="a09f7-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="a09f7-104">Для успешного развертывания Lync Server 2013 вам потребуется Windows PowerShell 3,0 на каждом компьютере, входящем в вашу топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a09f7-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="a09f7-105">Теперь для систем под управлением Windows Server 2012 или Windows Server 2012 R2 вам не нужно ничего делать и перейти к следующему этапу развертывания, так как PowerShell 3,0 включен в эти операционные системы.</span><span class="sxs-lookup"><span data-stu-id="a09f7-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a09f7-106">Но для систем под управлением Windows Server 2008 R2 с пакетом обновления 1 (SP1) перед установкой Lync Server 2013 вам потребуется установить оболочку PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a09f7-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="a09f7-107">Чтобы установить PowerShell 3,0, обратитесь к разделу <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="a09f7-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="a09f7-108">Это прямая ссылка на страницу загрузки PowerShell 3,0, а также сведения об их успешном установке.</span><span class="sxs-lookup"><span data-stu-id="a09f7-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="a09f7-109">После завершения установки или необходимо убедиться, что перед продолжением развертывания Lync Server необходимо убедиться, что PowerShell 3,0 находится на сервере, что происходит очень просто.</span><span class="sxs-lookup"><span data-stu-id="a09f7-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="a09f7-110">На сервере, который нужно проверить, нажмите кнопку **Пуск**, выберите **все программы**, **стандартные**, щелкните **Windows PowerShell**и выберите **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a09f7-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="a09f7-111">В консоли Windows PowerShell введите в командной строки следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="a09f7-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="a09f7-112">Если вы установили Windows PowerShell 3,0, вы увидите следующий результат:</span><span class="sxs-lookup"><span data-stu-id="a09f7-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

