---
title: Настройка узла-наблюдателя для использования проверки подлинности на доверенных серверах
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba69980f97e901703f51f71729c661821e70e61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="a4ca8-102">Настройка узла-наблюдателя в Lync Server 2013 для использования проверки подлинности на доверенных серверах</span><span class="sxs-lookup"><span data-stu-id="a4ca8-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4ca8-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a4ca8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a4ca8-104">Если компьютер узла-наблюдателя размещен внутри сети периметра, использование проверки подлинности "Доверенный сервер" значительно снижает административные затраты на обслуживание одного сертификата, а не паролей многочисленных учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="a4ca8-p101">Первым шагом в настройке проверки подлинности "Доверенный сервер" является создание доверенного пула приложений для размещения компьютера узла-наблюдателя. После создания доверенного пула приложений необходимо настроить искусственные транзакции в этом узле-наблюдателе для выполнения в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a4ca8-107">Доверенное приложение — это приложение, которое получает состояние Trusted для запуска в составе Lync Server 2013, но это не Встроенная часть продукта.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="a4ca8-108">Состояние доверенного приложения означает, что приложение не должно будет проходить проверку подлинности при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="a4ca8-109">Чтобы создать пул доверенных приложений, откройте командную консоль Lync Server 2013 и выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="a4ca8-110">Для получения сведений о параметрах, используемых в предыдущей команде, введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="a4ca8-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="a4ca8-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="a4ca8-112">После создания пула доверенных приложений настройте компьютер узла-наблюдателя для выполнения искусственных транзакций в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="a4ca8-113">Это можно сделать с помощью командлета **New-CsTrustedApplication** и команды, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="a4ca8-114">После завершения выполнения предыдущей команды и создания доверенного приложения выполните командлет Enable-CsTopology, чтобы убедиться, что изменения вступили в силу:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="a4ca8-115">После выполнения командлета Enable-CsTopology рекомендуется перезапустить компьютер.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="a4ca8-116">Чтобы убедиться в том, что создано новое доверенное приложение, введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="a4ca8-117">Настройка сертификата по умолчанию в узле-наблюдателе</span><span class="sxs-lookup"><span data-stu-id="a4ca8-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="a4ca8-118">Каждому узлу-наблюдателю должен быть назначен сертификат по умолчанию с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="a4ca8-119">**Чтобы назначить сертификат по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="a4ca8-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="a4ca8-120">Нажмите кнопку **Пуск**, выберите **все программы**, **Lync Server**, а затем щелкните **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="a4ca8-121">В мастере развертывания Lync Server щелкните **установить или обновить систему Lync Server** , а затем щелкните **выполнить** под заголовком **запрос, установка или назначение сертификата**.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a4ca8-122">Если кнопка <STRONG>Выполнить</STRONG> не активна, может понадобиться щелкнуть пункт <STRONG>Выполнить</STRONG> в разделе <STRONG>Установка локального хранилища конфигурации</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="a4ca8-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="a4ca8-p104">Если уже имеется сертификат, который может быть использован как сертификат по умолчанию, щелкните **По умолчанию** в мастере сертификатов, затем щелкните **Назначить**. Выполните действия, приведенные в мастере назначения сертификатов, чтобы назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="a4ca8-p105">Если необходимо запросить сертификат для использования в качестве сертификата по умолчанию, нажмите **Запрос**, затем выполните действия в мастере запроса сертификатов. Если использовать значения по умолчанию для сертификата веб-сервера, будет получен сертификат, который можно назначить в качестве сертификата по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="a4ca8-128">Установка и настройка узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="a4ca8-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="a4ca8-129">После перезапуска компьютера узла-наблюдателя и настройки сертификата необходимо запустить файл Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="a4ca8-130">(Необходимо запустить Watchernode. msi на компьютере, на котором установлены файлы агента Operations Manager и основные компоненты Lync Server 2013.)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="a4ca8-131">**Чтобы установить и настроить узел-наблюдатель**</span><span class="sxs-lookup"><span data-stu-id="a4ca8-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="a4ca8-132">Откройте командную консоль Lync Server, нажав кнопку **Пуск**, последовательно выбрав пункты **все программы**, **Lync Server**, а затем выбрав **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a4ca8-133">В командной консоли Lync Server введите следующую команду и нажмите клавишу ВВОД (укажите фактический путь к копии Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="a4ca8-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a4ca8-p107">Файл Watchernode.msi также можно выполнить из командного окна. Чтобы открыть командное окно, нажмите кнопку <STRONG>Пуск</STRONG>, щелкните правой кнопкой мыши пункт <STRONG>Командная строка</STRONG> и выберите <STRONG>Запуск от имени администратора</STRONG>. Когда командное окно откроется, введите команду, приведенную выше.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="a4ca8-p108">Обратите внимание, что сочетание имя/значение в предыдущей команде Authentication=TrustedServer зависит от регистра. Необходимо в точности повторить приведенную строчку. Следующая команда завершится с ошибкой, так как в ней не используется надлежащий регистр букв:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="a4ca8-140">C:\\Tools\\Watchernode. msi Authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="a4ca8-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="a4ca8-p109">Режим TrustedServer может использоваться только с компьютерами, которые находятся внутри сети периметра. Когда узел-наблюдатель работает в режиме TrustedServer, администраторы не должны поддерживать на этом компьютере пароли тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

