---
title: 'Lync Server 2013: установка пароля учетной записи Kerberos для проверки подлинности на сервере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="f1a7f-102">Установка пароля учетной записи Kerberos для проверки подлинности на сервере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1a7f-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1a7f-103">_**Тема последнего изменения:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="f1a7f-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="f1a7f-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="f1a7f-105">Необходимо настроить пароль для учетной записи Kerberos для каждого сайта, который содержит серверы переднего плана, серверы стандартных выпусков и режиссеров.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="f1a7f-106">Вы можете настроить пароль, запустив командлет **Set-кскерберосаккаунтпассворд** Windows PowerShell на одном сервере сайта (например, на одном сервере переднего плана).</span><span class="sxs-lookup"><span data-stu-id="f1a7f-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="f1a7f-107">Для каждого сайта необходимо выполнить командлет **Set-кскерберосаккаунтпассворд** .</span><span class="sxs-lookup"><span data-stu-id="f1a7f-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="f1a7f-108">Командлет настраивает службы IIS для службы веб-служб, а затем задает пароль для учетной записи компьютера в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="f1a7f-109">Альтернативный метод, зависящий от того, какой параметр используется с командлетом, настраивает IIS на одном сервере при использовании другого сервера, настроенного в качестве источника пароля учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="f1a7f-110">При использовании командлета **Set-кскерберосаккаунтпассворд** для задания пароля Kerberos устанавливает пароль в строку, сгенерированную случайным образом.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="f1a7f-111">Этот командлет связывается со всеми экземплярами служб IIS на всех центральных сайтах Lync Server 2013, которым назначена эта учетная запись.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="f1a7f-112">Настройка пароля для учетной записи проверки подлинности Kerberos</span><span class="sxs-lookup"><span data-stu-id="f1a7f-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="f1a7f-113">Войдите на любой компьютер домена с помощью командной консоли Lync Server Management Shell, установленной как участник группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f1a7f-114">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1a7f-115">В командной строке выполните следующие две команды:</span><span class="sxs-lookup"><span data-stu-id="f1a7f-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="f1a7f-116">Например:</span><span class="sxs-lookup"><span data-stu-id="f1a7f-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1a7f-117">Параметр UserAccount необходимо указать с помощью формата домен \ пользователь.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="f1a7f-118">Формат User@Domain. расширение не поддерживается для ссылок на объект компьютера, созданный для целей проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1a7f-119">После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f1a7f-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

