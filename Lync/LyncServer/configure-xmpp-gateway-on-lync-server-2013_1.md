---
title: Настройка шлюза КСМПП на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c7cec94a65a35f4f5141950c4691fec0b28706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="e4528-102">Настройка шлюза КСМПП на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4528-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4528-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e4528-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e4528-104">Если вы настраиваете политики для поддержки федеративных партнеров по протоколу расширенного обмена сообщениями (КСМПП), политики применяются к пользователям КСМПП федеративных доменов, но не к пользователям служб мгновенных сообщений в протоколе запуска сеансов (SIP). (например, Windows Live) или федеративные домены SIP.</span><span class="sxs-lookup"><span data-stu-id="e4528-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="e4528-105">Вы настраиваете федеративного партнера КСМПП для каждого КСМПП федеративного домена, с которым вы хотите разрешить пользователям добавлять контакты и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="e4528-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="e4528-106">После того как политики будут установлены, дополнительные задачи включают настройку сертификатов шлюза КСМПП, развертывание шлюза Lync Server 2013 КСМПП и, наконец, обновление записей DNS для шлюза КСМПП.</span><span class="sxs-lookup"><span data-stu-id="e4528-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="e4528-107">Настройка сертификатов шлюза КСМПП на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4528-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e4528-108">На пограничном сервере в мастере развертывания рядом с **шагом 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="e4528-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e4528-109">Если пограничный сервер развертывается в первый раз, вместо повторного запуска вы увидите "запустить".</span><span class="sxs-lookup"><span data-stu-id="e4528-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="e4528-110">На странице **Доступные задачи сертификатов** щелкните команду **Создать новый запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="e4528-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="e4528-111">На странице **запроса сертификата** выберите **внешний Граничный сертификат**.</span><span class="sxs-lookup"><span data-stu-id="e4528-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="e4528-112">На странице **отложенный или немедленный запрос** установите флажок **подготовить запрос сейчас, но отправить позже** .</span><span class="sxs-lookup"><span data-stu-id="e4528-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="e4528-113">На странице " **файл запроса сертификата** " введите полный путь и имя файла, в который нужно сохранить запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="e4528-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="e4528-114">На странице " **Укажите другой шаблон сертификата** ", чтобы использовать шаблон, отличный от шаблона веб-сервера по умолчанию, установите флажок **использовать альтернативный шаблон сертификата для выбранного центра сертификации** .</span><span class="sxs-lookup"><span data-stu-id="e4528-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="e4528-115">На странице **имя и параметры безопасности** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e4528-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="e4528-116">В поле **понятное имя**введите отображаемое имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="e4528-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="e4528-117">В качестве **битовой длины**укажите длину в битах (обычно это значение по умолчанию — 2048).</span><span class="sxs-lookup"><span data-stu-id="e4528-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="e4528-118">Убедитесь, что установлен флажок " **помечать закрытый ключ сертификата как экспортируемый** ".</span><span class="sxs-lookup"><span data-stu-id="e4528-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="e4528-119">На странице " **сведения об организации** " введите имя Организации и организационное подразделение (например, "подразделение" или "Отдел").</span><span class="sxs-lookup"><span data-stu-id="e4528-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="e4528-120">На странице **сведения о географическом** расположении укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="e4528-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="e4528-121">На странице **имя субъекта/альтернативная тема** отображается информация, которая будет автоматически заполнена мастером.</span><span class="sxs-lookup"><span data-stu-id="e4528-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="e4528-122">Если требуются дополнительные альтернативные имена субъектов, их можно указать в следующих двух шагах.</span><span class="sxs-lookup"><span data-stu-id="e4528-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="e4528-123">В **параметрах домена SIP на странице "альтернативные имена тем" (SAN)** установите флажок домен, чтобы добавить SIP. \<сипдомаин\> элемент в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="e4528-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="e4528-124">На странице **Настройка дополнительных имен для других тем** укажите необходимые дополнительные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="e4528-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e4528-125">Если установлен прокси-сервер КСМПП, по умолчанию доменное имя (например, contoso.com) заполнено в записях сети SAN.</span><span class="sxs-lookup"><span data-stu-id="e4528-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="e4528-126">Если вам нужны дополнительные элементы, добавьте их на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="e4528-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="e4528-127">На странице **сводки запроса** ознакомьтесь со сведениями о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="e4528-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="e4528-128">После завершения выполнения команд можно **Просмотреть журнал**или нажать кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="e4528-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="e4528-129">На странице " **файл запроса на сертификат** " можно просмотреть созданный файл запроса на подписывание сертификата (CSR), щелкнув Просмотреть или выйти из мастера сертификатов, нажав кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e4528-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="e4528-130">Скопируйте файл запроса и отправьте его в общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="e4528-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="e4528-131">После получения, импорта и назначения общедоступного сертификата вы должны остановить и перезапустить службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e4528-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="e4528-132">Для этого введите в консоль управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e4528-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e4528-133">Настройка нового шлюза Lync Server 2013 КСМПП</span><span class="sxs-lookup"><span data-stu-id="e4528-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e4528-134">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4528-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="e4528-135">На панели навигации слева выберите пункт **интеграция и внешний доступ** , а затем — **КСМПП Федеративные партнеры**.</span><span class="sxs-lookup"><span data-stu-id="e4528-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="e4528-136">Чтобы создать новую конфигурацию, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="e4528-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="e4528-137">Определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e4528-137">Define the following settings:</span></span>

5.  <span data-ttu-id="e4528-138">**Основной домен**     (обязательно).</span><span class="sxs-lookup"><span data-stu-id="e4528-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="e4528-139">Основной домен — это базовый домен партнера КСМПП.</span><span class="sxs-lookup"><span data-stu-id="e4528-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="e4528-140">Например, вы можете ввести **Fabrikam.com** для доменного имени КСМПП партнера.</span><span class="sxs-lookup"><span data-stu-id="e4528-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="e4528-141">Это обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e4528-141">This is a required entry.</span></span>

6.  <span data-ttu-id="e4528-142">**Описание**   описание для заметок или другой идентифицирующей информации о конкретной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4528-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="e4528-143">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e4528-143">This entry is optional.</span></span>

7.  <span data-ttu-id="e4528-144">**Дополнительные домены**   дополнительные домены — это домены, которые входят в состав домена вашего партнера КСМПП, который должен быть включен в рамках разрешенного КСМПП общения.</span><span class="sxs-lookup"><span data-stu-id="e4528-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="e4528-145">Например, если основной домен — **Fabrikam.com**, вы увидите список всех остальных доменов, которые находятся в Fabrikam.com, с которыми вы будете общаться с помощью КСМПП.</span><span class="sxs-lookup"><span data-stu-id="e4528-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="e4528-146">**Тип**   партнера. **тип партнера** является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="e4528-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="e4528-147">Чтобы описать и принудительно добавить контакты, необходимо выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e4528-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="e4528-148">Вы можете выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e4528-148">You can select from:</span></span>
    
      - <span data-ttu-id="e4528-149">**Федеративное** Тип **федеративного** партнера представляет высокий уровень доверия между развертыванием Lync Server и партнером по КСМПП.</span><span class="sxs-lookup"><span data-stu-id="e4528-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="e4528-150">Этот тип партнера рекомендуется использовать для Федерации с серверами КСМПП в рамках одного предприятия или там, где есть установленная деловая связь.</span><span class="sxs-lookup"><span data-stu-id="e4528-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="e4528-151">КСМППные контакты в федеративных партнерах могут:</span><span class="sxs-lookup"><span data-stu-id="e4528-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="e4528-152">Добавляйте контакты Lync и просматривайте их присутствие без использования быстрой авторизации пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="e4528-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="e4528-153">Отправляйте мгновенные сообщения в контакты Lync, не добавляя ли пользователь Lync в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="e4528-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="e4528-154">Ознакомьтесь с заметками о состоянии пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="e4528-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="e4528-155">\*\*\*\* Общедоступная проверенная **Проверка подлинности партнера является** общедоступным поставщиком КСМПП, который является надежным для проверки личности пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4528-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="e4528-156">КСМППные контакты в общедоступной проверенной сети могут добавлять контакты Lync и просматривать их присутствие и отправлять мгновенные сообщения без явного разрешения пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="e4528-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="e4528-157">КСМПП контакты в общедоступной проверенной сети никогда не видят заметок о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="e4528-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="e4528-158">Этот параметр не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e4528-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="e4528-159">**Общедоступная непроверенная** **Общедоступный непроверенный** партнер — это общедоступный поставщик КСМПП, который не является доверенным для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4528-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="e4528-160">Пользователи КСМПП в общедоступных непроверенных сетях не смогут общаться с пользователями Lync, если пользователь Lync явно не предоставил их, добавив их в список контактов.</span><span class="sxs-lookup"><span data-stu-id="e4528-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="e4528-161">Пользователи КСМПП в общедоступных непроверенных сетях не увидят заметок о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="e4528-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="e4528-162">Этот параметр рекомендуется использовать для любой Федерации с общедоступными поставщиками КСМПП, такими как Google поговорить.</span><span class="sxs-lookup"><span data-stu-id="e4528-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="e4528-163">**Тип подключения:** Определяет различные параметры правил и диалбакк.</span><span class="sxs-lookup"><span data-stu-id="e4528-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="e4528-164">**Согласование TLS определяет**   правила согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="e4528-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="e4528-165">Для службы КСМПП может потребоваться TLS, может быть необязательным TLS или определено, что TLS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e4528-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="e4528-166">Если выбрать необязательный вариант, вы не сможете получить требование к службе КСМПП для решения, которое является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="e4528-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="e4528-167">Чтобы просмотреть все возможные параметры и сведения о согласовании SASL, TLS и Диалбакк, в том числе недопустимых и известных конфигураций ошибок, — [в разделе Параметры согласования КСМПП федеративных партнеров в Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="e4528-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="e4528-168">**Для службы КСМПП требуется**согласование TLS.   </span><span class="sxs-lookup"><span data-stu-id="e4528-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="e4528-169">**Необязательная**   служба КСМПП указывает на то, что TLS является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="e4528-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e4528-170">**Не поддерживается**   служба КСМПП не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="e4528-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="e4528-171">**Согласование SASL определяет**   правила согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="e4528-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="e4528-172">Служба КСМПП может потребовать SASL, может сделать SASL необязательной или определить, что SASL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e4528-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="e4528-173">Если выбрать необязательный вариант, вы не сможете получить требование к службе КСМПП партнера, чтобы принять решение для принудительного согласования.</span><span class="sxs-lookup"><span data-stu-id="e4528-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="e4528-174">**Для службы КСМПП требуется**согласование SASL.   </span><span class="sxs-lookup"><span data-stu-id="e4528-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="e4528-175">**Необязательная**   служба КСМПП указывает, что SASL является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="e4528-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e4528-176">**Не поддерживается**   служба КСМПП не поддерживает SASL.</span><span class="sxs-lookup"><span data-stu-id="e4528-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="e4528-177">**Диалбакк согласование серверной поддержки** Сервер службы поддержки диалбакк использует систему доменных имен (DNS) и удостоверяющий сервер, чтобы убедиться, что запрос был получен от действующего партнера КСМПП.</span><span class="sxs-lookup"><span data-stu-id="e4528-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="e4528-178">Для этого на исходном сервере создается сообщение определенного типа с созданным ключом диалбакк и выполняется поиск сервера-получателя в DNS.</span><span class="sxs-lookup"><span data-stu-id="e4528-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="e4528-179">Сервер-источник отправляет ключ в потоке XML в конечный поиск DNS, предположительно на получающем сервере.</span><span class="sxs-lookup"><span data-stu-id="e4528-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="e4528-180">При получении ключа над потоком XML, принимающий сервер не отвечает на исходный сервер, но отправляет ключ на известный полномочный сервер.</span><span class="sxs-lookup"><span data-stu-id="e4528-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="e4528-181">Удостоверяющий сервер проверяет, является ли ключ допустимым или недействительным.</span><span class="sxs-lookup"><span data-stu-id="e4528-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="e4528-182">Если это значение недействительно, принимающий сервер не отвечает на исходящий сервер.</span><span class="sxs-lookup"><span data-stu-id="e4528-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="e4528-183">Если ключ является действительным, принимающий сервер информирует сервер источника о том, что удостоверение и ключ являются допустимыми, и может быть инициировано обсуждение.</span><span class="sxs-lookup"><span data-stu-id="e4528-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="e4528-184">Существует два допустимых состояния для **согласования диалбакк**:</span><span class="sxs-lookup"><span data-stu-id="e4528-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="e4528-185">**True**   : сервер КСМПП настроен на использование согласования диалбакк, если требуется получить запрос от сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="e4528-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="e4528-186">**False**   . сервер КСМПП не настроен на использование согласования диалбакк и если запрос должен быть получен от сервера-источника, он будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="e4528-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="e4528-187">Нажмите **кнопку Сохранить,** чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="e4528-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e4528-188">Обновление записей DNS для Lync Server 2013 КСМПП Gateway</span><span class="sxs-lookup"><span data-stu-id="e4528-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e4528-189">Чтобы настроить DNS для КСМПП Федерации, добавьте следующую запись SRV на внешний DNS-сервер:\_КСМПП-Server. \_протокол TCP. \<доменное\> имя. SRV-запись будет СОПОСТАВЛЕНа с полным доменным именем EDGE на пограничном сервере с таким же значением порта 5269.</span><span class="sxs-lookup"><span data-stu-id="e4528-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

