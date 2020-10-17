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
ms.openlocfilehash: 4ac886bf4eba4261a733241aa8d1d5396c4acc86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523856"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="6bbd5-102">Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bbd5-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bbd5-103">_**Последнее изменение темы:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="6bbd5-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="6bbd5-104">Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="6bbd5-105">На сайте серверы переднего плана, серверы Standard Edition и директора могут использовать учетную запись проверки подлинности Kerberos для проверки подлинности запросов к службе веб-служб.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="6bbd5-106">Эта процедура размещает каждый сервер, на котором запущены веб-службы, на сайте, которому была назначена учетная запись Kerberos, и обновляет параметры конфигурации служб IIS для использования учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="6bbd5-107">Для получения дополнительных сведений см. Введите [пароль учетной записи проверки подлинности Kerberos на сервере в Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bbd5-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="6bbd5-108">Порядок задания и настройки пароля учетной записи проверки подлинности Kerberos</span><span class="sxs-lookup"><span data-stu-id="6bbd5-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="6bbd5-109">Войдите в систему исходного компьютера (например, fe01.contoso.com) в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6bbd5-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6bbd5-111">В командной строке Командная консоль Lync Server выполните две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="6bbd5-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="6bbd5-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="6bbd5-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6bbd5-p102">Имена исходного и конечного компьютеров должны быть полными доменными именами (FQDN) сервера. Имя FQDN пула можно использовать только в том случае, если имя пула совпадает с именем компьютера, который используется в качестве исходного или конечного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6bbd5-115">После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bbd5-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

