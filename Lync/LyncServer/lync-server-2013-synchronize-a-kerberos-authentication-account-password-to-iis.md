---
title: Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="2a57d-102">Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a57d-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a57d-103">_**Тема последнего изменения:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="2a57d-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="2a57d-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2a57d-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2a57d-105">На сайте, серверы переднего плана, серверы Standard Edition и режиссеры могут использовать учетную запись проверки подлинности Kerberos для проверки подлинности запросов к службе веб-служб.</span><span class="sxs-lookup"><span data-stu-id="2a57d-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="2a57d-106">Эта процедура позволяет найти каждый сервер, на котором запущены веб-службы, на сайте, которому была назначена учетная запись Kerberos, и обновить параметры конфигурации служб IIS для использования учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2a57d-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="2a57d-107">Дополнительные сведения можно найти в разделе [определение пароля учетной записи проверки подлинности Kerberos на сервере Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="2a57d-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="2a57d-108">Установка и Настройка пароля учетной записи для проверки подлинности Kerberos</span><span class="sxs-lookup"><span data-stu-id="2a57d-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="2a57d-109">Войдите в систему исходного компьютера (например, fe01.contoso.com) в качестве участника группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2a57d-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2a57d-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a57d-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2a57d-111">В командной строке оболочки Lync Server Management Shell выполните следующие две команды:</span><span class="sxs-lookup"><span data-stu-id="2a57d-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="2a57d-112">Например:</span><span class="sxs-lookup"><span data-stu-id="2a57d-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2a57d-113">Имя исходного компьютера и конечного компьютера должно быть полным доменным именем сервера.</span><span class="sxs-lookup"><span data-stu-id="2a57d-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="2a57d-114">Полное доменное имя пула нельзя использовать, если оно не совпадает с именем компьютера, который используется в качестве исходного компьютера или конечного компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a57d-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2a57d-115">После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2a57d-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

