---
title: Настройка шлюза КСМПП на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5609ecc72e43c28c87f9cdab1a4a7be93b89bf8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="151da-102">Настройка шлюза КСМПП на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="151da-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="151da-103">_**Тема последнего изменения:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="151da-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="151da-104">Последние шаги для миграции шлюза КСМПП: Настройка сертификатов для пограничного сервера Lync Server 2013, развертывание шлюза Lync Server 2013 КСМПП и обновление записей DNS для шлюза КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="151da-105">Эти действия должны выполняться параллельно, чтобы свести к минимуму время, установленное на вашем шлюзе КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="151da-106">Перед выполнением описанных ниже действий необходимо переместить всех пользователей в развертывание Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="151da-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="151da-107">КСМПП Федерация не поддерживается для пользователей, которые размещаются на устройствах с возможностью бесперебойной ветви.</span><span class="sxs-lookup"><span data-stu-id="151da-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="151da-108">Это относится и к сведениям о присутствии, и по обмену МГНОВЕНными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="151da-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="151da-109">Настройка сертификатов шлюза КСМПП на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="151da-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="151da-110">На пограничном сервере в мастере развертывания рядом с **шагом 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="151da-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="151da-111">Если пограничный сервер развертывается в первый раз, вместо повторного запуска вы увидите "запустить".</span><span class="sxs-lookup"><span data-stu-id="151da-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="151da-112">На странице **Доступные задачи сертификатов** щелкните команду **Создать новый запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="151da-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="151da-113">На странице **запроса сертификата** выберите **внешний Граничный сертификат**.</span><span class="sxs-lookup"><span data-stu-id="151da-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="151da-114">На странице **отложенный или немедленный запрос** установите флажок **подготовить запрос сейчас, но отправить позже** .</span><span class="sxs-lookup"><span data-stu-id="151da-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="151da-115">На странице " **файл запроса сертификата** " введите полный путь и имя файла, в который нужно сохранить запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="151da-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="151da-116">На странице " **Укажите другой шаблон сертификата** ", чтобы использовать шаблон, отличный от шаблона веб-сервера по умолчанию, установите флажок **использовать альтернативный шаблон сертификата для выбранного центра сертификации** .</span><span class="sxs-lookup"><span data-stu-id="151da-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="151da-117">На странице **имя и параметры безопасности** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="151da-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="151da-118">В поле **понятное имя**введите отображаемое имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="151da-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="151da-119">В качестве **битовой длины**укажите длину в битах (обычно это значение по умолчанию — 2048).</span><span class="sxs-lookup"><span data-stu-id="151da-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="151da-120">Убедитесь, что установлен флажок " **помечать закрытый ключ сертификата как экспортируемый** ".</span><span class="sxs-lookup"><span data-stu-id="151da-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="151da-121">На странице " **сведения об организации** " введите имя Организации и организационное подразделение (например, "подразделение" или "Отдел").</span><span class="sxs-lookup"><span data-stu-id="151da-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="151da-122">На странице **сведения о географическом** расположении укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="151da-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="151da-123">На странице **имя субъекта/альтернативная тема** отображается информация, которая будет автоматически заполнена мастером.</span><span class="sxs-lookup"><span data-stu-id="151da-123">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="151da-124">Если требуются дополнительные альтернативные имена субъектов, их можно указать в следующих двух шагах.</span><span class="sxs-lookup"><span data-stu-id="151da-124">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="151da-125">В **параметрах домена SIP на странице "альтернативные имена тем" (SAN)** установите флажок домен, чтобы добавить SIP. \<сипдомаин\> элемент в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="151da-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="151da-126">На странице **Настройка дополнительных имен для других тем** укажите необходимые дополнительные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="151da-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="151da-127">Если установлен прокси-сервер КСМПП, по умолчанию доменное имя (например, contoso.com) заполнено в записях сети SAN.</span><span class="sxs-lookup"><span data-stu-id="151da-127">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="151da-128">Если вам нужны дополнительные элементы, добавьте их на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="151da-128">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="151da-129">На странице **сводки запроса** ознакомьтесь со сведениями о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="151da-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="151da-130">После завершения выполнения команд можно **Просмотреть журнал**или нажать кнопку Далее, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="151da-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="151da-131">На странице " **файл запроса на сертификат** " можно просмотреть созданный файл запроса на подписывание сертификата (CSR), щелкнув **Просмотреть** или выйти из мастера сертификатов, нажав кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="151da-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="151da-132">Скопируйте файл запроса и отправьте его в общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="151da-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="151da-133">После получения, импорта и назначения общедоступного сертификата вы должны остановить и перезапустить службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="151da-133">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="151da-134">Для этого введите в консоль управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="151da-134">You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="151da-135">Настройка нового шлюза Lync Server 2013 КСМПП</span><span class="sxs-lookup"><span data-stu-id="151da-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="151da-136">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="151da-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="151da-137">На панели навигации слева выберите пункт **интеграция и внешний доступ** , а затем — **КСМПП Федеративные партнеры**.</span><span class="sxs-lookup"><span data-stu-id="151da-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="151da-138">Чтобы создать новую конфигурацию, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="151da-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="151da-139">Определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="151da-139">Define the following settings:</span></span>

5.  <span data-ttu-id="151da-140">**Основной домен**     (обязательно).</span><span class="sxs-lookup"><span data-stu-id="151da-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="151da-141">Основной домен — это базовый домен партнера КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="151da-142">Например, вы можете ввести **Fabrikam.com** для доменного имени КСМПП партнера.</span><span class="sxs-lookup"><span data-stu-id="151da-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="151da-143">Это обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="151da-143">This is a required entry.</span></span>

6.  <span data-ttu-id="151da-144">**Описание**   описание для заметок или другой идентифицирующей информации о конкретной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="151da-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="151da-145">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="151da-145">This entry is optional.</span></span>

7.  <span data-ttu-id="151da-146">**Дополнительные домены**   дополнительные домены — это домены, которые входят в состав домена вашего партнера КСМПП, который должен быть включен в рамках разрешенного КСМПП общения.</span><span class="sxs-lookup"><span data-stu-id="151da-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="151da-147">Например, если основной домен — **Fabrikam.com**, вы увидите список всех остальных доменов, которые находятся в Fabrikam.com, с которыми вы будете общаться с помощью КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="151da-148">**Тип**   партнера. **тип партнера** является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="151da-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="151da-149">Чтобы описать и принудительно добавить контакты, необходимо выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="151da-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="151da-150">Вы можете выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="151da-150">You can select from:</span></span>
    
      - <span data-ttu-id="151da-151">**Федеративный**   тип **федеративного** партнера представляет высокий уровень доверия между развертыванием Lync Server и партнером по КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="151da-152">Этот тип партнера рекомендуется использовать для Федерации с серверами КСМПП в рамках одного предприятия или там, где есть установленная деловая связь.</span><span class="sxs-lookup"><span data-stu-id="151da-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="151da-153">КСМППные контакты в федеративных партнерах могут:</span><span class="sxs-lookup"><span data-stu-id="151da-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="151da-154">Добавляйте контакты Lync и просматривайте их присутствие без использования быстрой авторизации пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="151da-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="151da-155">Отправляйте мгновенные сообщения в контакты Lync, не добавляя ли пользователь Lync в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="151da-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="151da-156">Ознакомьтесь с заметками о состоянии пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="151da-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="151da-157">\*\*\*\*   Общедоступная \*\*\*\* проверенная проверка подлинности партнера является общедоступным поставщиком КСМПП, который является надежным для проверки личности пользователей.</span><span class="sxs-lookup"><span data-stu-id="151da-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="151da-158">КСМППные контакты в общедоступной проверенной сети могут добавлять контакты Lync и просматривать их присутствие и отправлять мгновенные сообщения без явного разрешения пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="151da-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="151da-159">КСМПП контакты в общедоступной проверенной сети никогда не видят заметок о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="151da-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="151da-160">Этот параметр не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="151da-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="151da-161">\*\*\*\* Общедоступный непроверенный партнер является общедоступным поставщиком КСМПП, который не является доверенным для проверки подлинности пользователей. \*\*\*\*    </span><span class="sxs-lookup"><span data-stu-id="151da-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="151da-162">Пользователи КСМПП в общедоступных непроверенных сетях не смогут общаться с пользователями Lync, если пользователь Lync явно не предоставил их, добавив их в список контактов.</span><span class="sxs-lookup"><span data-stu-id="151da-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="151da-163">Пользователи КСМПП в общедоступных непроверенных сетях не увидят заметок о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="151da-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="151da-164">Этот параметр рекомендуется использовать для любой Федерации с общедоступными поставщиками КСМПП, такими как Google поговорить.</span><span class="sxs-lookup"><span data-stu-id="151da-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="151da-165">**Тип подключения:** Определяет различные параметры правил и диалбакк.</span><span class="sxs-lookup"><span data-stu-id="151da-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="151da-166">**Согласование TLS определяет**   правила согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="151da-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="151da-167">Для службы КСМПП может потребоваться TLS, может быть необязательным TLS или определено, что TLS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="151da-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="151da-168">Если выбрать необязательный вариант, вы не сможете получить требование к службе КСМПП для решения, которое является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="151da-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="151da-169">Чтобы просмотреть все возможные параметры и сведения о согласовании SASL, TLS и Диалбакк, в том числе недопустимых и известных конфигураций ошибок, — [в разделе Параметры согласования КСМПП федеративных партнеров в Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="151da-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-170">\*\*\*\* Для службы КСМПП требуется согласование TLS.   </span><span class="sxs-lookup"><span data-stu-id="151da-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-171">\*\*\*\*   Необязательная служба КСМПП указывает на то, что TLS является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="151da-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-172">**Не поддерживается**   служба КСМПП не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="151da-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="151da-173">**Согласование SASL определяет**   правила согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="151da-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="151da-174">Служба КСМПП может потребовать SASL, может сделать SASL необязательной или определить, что SASL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="151da-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="151da-175">Если выбрать необязательный вариант, вы не сможете получить требование к службе КСМПП партнера, чтобы принять решение для принудительного согласования.</span><span class="sxs-lookup"><span data-stu-id="151da-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-176">\*\*\*\* Для службы КСМПП требуется согласование SASL.   </span><span class="sxs-lookup"><span data-stu-id="151da-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-177">\*\*\*\*   Необязательная служба КСМПП указывает, что SASL является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="151da-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-178">**Не поддерживается**   служба КСМПП не поддерживает SASL.</span><span class="sxs-lookup"><span data-stu-id="151da-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="151da-179">**Диалбакк согласование серверной поддержки** Сервер службы поддержки диалбакк использует систему доменных имен (DNS) и удостоверяющий сервер, чтобы убедиться, что запрос был получен от действующего партнера КСМПП.</span><span class="sxs-lookup"><span data-stu-id="151da-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="151da-180">Для этого на исходном сервере создается сообщение определенного типа с созданным ключом диалбакк и выполняется поиск сервера-получателя в DNS.</span><span class="sxs-lookup"><span data-stu-id="151da-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="151da-181">Сервер-источник отправляет ключ в потоке XML в конечный поиск DNS, предположительно на получающем сервере.</span><span class="sxs-lookup"><span data-stu-id="151da-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="151da-182">При получении ключа над потоком XML, принимающий сервер не отвечает на исходный сервер, но отправляет ключ на известный полномочный сервер.</span><span class="sxs-lookup"><span data-stu-id="151da-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="151da-183">Удостоверяющий сервер проверяет, является ли ключ допустимым или недействительным.</span><span class="sxs-lookup"><span data-stu-id="151da-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="151da-184">Если это значение недействительно, принимающий сервер не отвечает на исходящий сервер.</span><span class="sxs-lookup"><span data-stu-id="151da-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="151da-185">Если ключ является действительным, принимающий сервер информирует сервер источника о том, что удостоверение и ключ являются допустимыми, и может быть инициировано обсуждение.</span><span class="sxs-lookup"><span data-stu-id="151da-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="151da-186">Существует два допустимых состояния для **согласования диалбакк**:</span><span class="sxs-lookup"><span data-stu-id="151da-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-187">**True**   : сервер КСМПП настроен на использование согласования диалбакк, если требуется получить запрос от сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="151da-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="151da-188">**False**   . сервер КСМПП не настроен на использование согласования диалбакк и если запрос должен быть получен от сервера-источника, он будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="151da-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="151da-189">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="151da-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="151da-190">Обновление записей DNS для Lync Server 2013 КСМПП Gateway</span><span class="sxs-lookup"><span data-stu-id="151da-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="151da-191">Чтобы настроить DNS для КСМПП Федерации, добавьте следующую запись SRV на внешний DNS-сервер:\_КСМПП-Server. \_протокол TCP. \<доменное\> имя. SRV-запись будет СОПОСТАВЛЕНа с полным доменным именем EDGE на пограничном сервере с таким же значением порта 5269.</span><span class="sxs-lookup"><span data-stu-id="151da-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

