---
title: Промежуточное хранение с использованием сертификатов AV и OAuth в Set-CsCertificate
description: Размещение сертификатов AV и OAuth с помощью Set — CsCertificate.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541845"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="da4a5-103">Промежуточные сертификаты AV и OAuth в Lync Server 2013 using in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="da4a5-103">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da4a5-104">_**Последнее изменение темы:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="da4a5-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="da4a5-105">Связь аудио-и видеоданных (A/V) является ключевым компонентом Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da4a5-105">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="da4a5-106">Такие функции, как общий доступ к приложениям, а также аудио-и видеоконференции, основываются на сертификатах, назначенных службе аудио-и видеоданных, а именно службе проверки подлинности A/V.</span><span class="sxs-lookup"><span data-stu-id="da4a5-106">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="da4a5-107">Эта новая функция разработана для работы с пограничной службой аудио-и видеоданных и сертификатом <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="da4a5-107">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="da4a5-108">Другие типы сертификатов можно подготовить к работе с пограничной службой аудио-и видеоданных и типом сертификата OAuth, но при этом не будет выгодно поведение сосуществования, которое будет иметь сертификат пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="da4a5-108">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="da4a5-109">Командлеты PowerShell для консоли управления Lync Server, используемые для управления сертификатами Microsoft Lync Server 2013, относятся к сертификатам пограничной службы аудио-и видеоданных в качестве типа сертификата <EM>AudioVideoAuthentication</EM> и сертификата OAuthServer в качестве типа <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="da4a5-109">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="da4a5-110">Для оставшейся части этого раздела и уникальной идентификации сертификатов они будут называться одинаковым типом идентификатора, <EM>AudioVideoAuthentication</EM> и <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="da4a5-110">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="da4a5-111">Служба проверки подлинности аудио- и видеоконференций отвечает за выдачу маркеров, используемых клиентами и другими пользователями аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="da4a5-111">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="da4a5-112">Маркеры создаются на основе атрибутов сертификата, и по истечении срока действия сертификата, происходит разрыв соединения или отображается запрос на повторное подключение с использованием нового маркера, созданного новым сертификатом.</span><span class="sxs-lookup"><span data-stu-id="da4a5-112">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="da4a5-113">Новая функция в Lync Server 2013 поможет решить эту проблему — возможность размещения нового сертификата перед старым сроком действия, позволяющая обоим сертификатам продолжать работать в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="da4a5-113">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="da4a5-114">Эта функция использует обновленные функции в командлете Set-CsCertificate Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="da4a5-114">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="da4a5-115">Новый параметр –Roll вместе с текущим параметром –EffectiveDate помещает новый сертификат AudioVideoAuthentication в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="da4a5-115">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="da4a5-116">Предыдущий сертификат AudioVideoAuthentication по-прежнему действует для проверки выданных маркеров.</span><span class="sxs-lookup"><span data-stu-id="da4a5-116">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="da4a5-117">С момента размещения нового сертификата AudioVideoAuthentication возникают следующие наборы событий:</span><span class="sxs-lookup"><span data-stu-id="da4a5-117">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="da4a5-118">С помощью командлетов командной консоли Lync Server для управления сертификатами можно запрашивать отдельный и отдельный сертификаты для каждой цели на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="da4a5-118">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="da4a5-119">С помощью мастера сертификатов в мастере развертывания Lync Server можно создавать сертификаты, но обычно это тип <STRONG>по умолчанию</STRONG> , который связывает все сертификаты, используемые для пограничного сервера, на один сертификат.</span><span class="sxs-lookup"><span data-stu-id="da4a5-119">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="da4a5-120">Если планируется применение компонента последовательных сертификатов, рекомендуется отделить сертификат AudioVideoAuthentication от других назначений сертификата.</span><span class="sxs-lookup"><span data-stu-id="da4a5-120">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="da4a5-121">Можно предоставить и разместить сертификат типа Default для промежуточного хранения, однако, только часть AudioVideoAuthentication объединенного сертификата сможет максимально эффективно использовать преимущества промежуточного хранения.</span><span class="sxs-lookup"><span data-stu-id="da4a5-121">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="da4a5-122">Пользователь, участвующий в (например,) беседу по обмену мгновенными сообщениями при истечении срока действия сертификата, должен выйти из системы и войти в нее, чтобы использовать новый сертификат, связанный со службой пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="da4a5-122">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="da4a5-123">Аналогичное поведение будет выполняться для пользователя, участвующего в веб-конференции с помощью пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="da4a5-123">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="da4a5-124">Сертификат OAuthTokenIssuer представляет собой отдельный тип, общий доступ к которому предоставляется для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="da4a5-124">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="da4a5-125">Вы создаете сертификат и управляете им в одном месте, а сертификат хранится в центральном хранилище управления для всех остальных серверов.</span><span class="sxs-lookup"><span data-stu-id="da4a5-125">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="da4a5-126">Для полного понимания возможностей и условий использования командлета Set-CsCertificate и использования его для промежуточного хранения сертификатов до истечения срока действия текущего сертификата требуются дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="da4a5-126">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="da4a5-127">Параметр –Roll имеет критически важное значение, но в целом, выполняет одну-единственную задачу.</span><span class="sxs-lookup"><span data-stu-id="da4a5-127">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="da4a5-128">Если задать его в качестве параметра, вы указываете Set-CsCertificate, что вы будете предоставлять сведения о сертификате, который будет зависеть от типа-Type (например, AudioVideoAuthentication и OAuthTokenIssuer), когда сертификат станет эффективным, определяемым параметром – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="da4a5-128">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="da4a5-129">**— Рулон:** Параметр – рулон является обязательным и содержит зависимости, которые необходимо указать вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="da4a5-129">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="da4a5-130">Обязательные параметры для полного определения того, какие сертификаты будут затронуты и как они будут применяться:</span><span class="sxs-lookup"><span data-stu-id="da4a5-130">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="da4a5-131">**— EffectiveDate:** Параметр – EffectiveDate определяет, когда новый сертификат становится совместным с текущим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="da4a5-131">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="da4a5-132">Параметр – EffectiveDate можно закрыть до истечения срока действия текущего сертификата или может быть более длительным.</span><span class="sxs-lookup"><span data-stu-id="da4a5-132">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="da4a5-133">Рекомендуемый минимум — EffectiveDate для сертификата AudioVideoAuthentication будет 8 часов, что является временем жизни токенов по умолчанию для маркеров служебной службы AV EDGE, выданных с помощью сертификата AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="da4a5-133">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="da4a5-p109">При размещении сертификатов OAuthTokenIssuer для промежуточного хранения действуют различные требования в отношении времени упреждения, прежде чем действие сертификата вступит в силу. Минимальное время упреждения для сертификата OAuthTokenIssuer составляет 24 часа до истечения срока действия текущего сертификата. Увеличение времени упреждения для совместной работы применяется в связи с тем, что другие роли сервера, зависимые от сертификата OAuthTokenIssuer (например, Exchange Server), для которых предусматривается более продолжительный срок хранения сертификатов, создают данные проверки подлинности и ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="da4a5-137">**— Thumbprint:** Отпечаток — это атрибут сертификата, который является уникальным для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="da4a5-137">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="da4a5-138">Параметр – Thumbprint используется для идентификации сертификата, на который повлияет действие командлета Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="da4a5-138">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="da4a5-139">**— Тип:** Параметр – Type может принимать один тип использования сертификата или список типов использования сертификатов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="da4a5-139">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="da4a5-140">Типы сертификатов — это те, которые идентифицируют командлет и на сервер, на котором находится сертификат.</span><span class="sxs-lookup"><span data-stu-id="da4a5-140">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="da4a5-141">Например, введите AudioVideoAuthentication для использования службой аудио-и видеоданных и службой проверки подлинности AV.</span><span class="sxs-lookup"><span data-stu-id="da4a5-141">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="da4a5-142">Если вы решите одновременно выполнять и резервное размещение сертификатов другого типа, необходимо учитывать максимально необходимое минимальное минимальное время ожидания для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="da4a5-142">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="da4a5-143">Например, необходимо выполнить промежуточное хранение сертификатов типа AudioVideoAuthentication и OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="da4a5-143">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="da4a5-144">Минимальное значение – EffectiveDate должно быть большим из двух сертификатов, в данном случае OAuthTokenIssuer, в котором минимальное время ожидания составляет 24 часа.</span><span class="sxs-lookup"><span data-stu-id="da4a5-144">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="da4a5-145">Если вы не хотите поAudioVideoAuthentication сертификат с временем ожидания в 24 часа, разработайте его отдельно с EffectiveDate, который больше требований.</span><span class="sxs-lookup"><span data-stu-id="da4a5-145">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="da4a5-146">Обновление или обновление сертификата пограничной службы аудио-и видеоданных с параметрами – рулон и-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="da4a5-146">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="da4a5-147">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="da4a5-147">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="da4a5-148">Запросить обновление или новый сертификат AudioVideoAuthentication с экспортируемым закрытым ключом для существующего сертификата в пограничной службе аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="da4a5-148">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="da4a5-149">Импортируйте новый сертификат AudioVideoAuthentication на пограничный сервер и весь другой пограничный сервер в пуле (при наличии развернутого пула).</span><span class="sxs-lookup"><span data-stu-id="da4a5-149">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="da4a5-150">Настройте импортированный сертификат с помощью командлета Set-CsCertificate и используйте параметр –Roll вместе с параметром –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="da4a5-150">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="da4a5-151">Дата вступления в силу определяется как время истечения срока действия текущего сертификата (14:00:00 или 14:00:00) за вычетом срока действия маркера (по умолчанию — восемь часов).</span><span class="sxs-lookup"><span data-stu-id="da4a5-151">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="da4a5-152">Это дает нам время, когда сертификат должен быть установлен в значение Active, а — значение параметра – EffectiveDate \<string\> : "7/22/2012 6:00:00 AM".</span><span class="sxs-lookup"><span data-stu-id="da4a5-152">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="da4a5-153">Для пограничного пула необходимо иметь все сертификаты AudioVideoAuthentication, развернутые и подготовленные в соответствии с датой и временем первого развернутого параметра – EffectiveDate первого сертификата, чтобы избежать возможного сбоя аудио-и видеосвязи из-за истечения срока действия старого сертификата до того, как все маркеры клиентов и потребителей будут обновлены с помощью нового сертификата.</span><span class="sxs-lookup"><span data-stu-id="da4a5-153">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="da4a5-154">Команда Set-CsCertificate с параметрами –Roll и –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="da4a5-154">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="da4a5-155">Пример команды Set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="da4a5-155">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="da4a5-p113">Параметр EffectiveDate должен быть отформатирован в соответствии с региональными и языковыми параметрами американского английского.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="da4a5-158">Визуальная временная шкала эффективна для более полного понимания процедуры, используемой командлетом Set-CsCertificate, параметрами -Roll и  -EffectiveDate для размещения новых сертификатов для промежуточного хранения в целях выдачи новых маркеров AudioVideoAuthentication при одновременном использовании существующего сертификата для проверки AudioVideoAuthentication, используемого пользователями.</span><span class="sxs-lookup"><span data-stu-id="da4a5-158">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="da4a5-159">В следующем примере администратор определяет срок действия сертификата пограничной службы аудио-и видеосвязи в 2:00:00 PM на 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="da4a5-159">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="da4a5-160">Он запрашивает и получает новый сертификат и импортирует его на каждый пограничный сервер в своем пуле.</span><span class="sxs-lookup"><span data-stu-id="da4a5-160">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="da4a5-161">В 2:00 07/22/2012 он начинает запуск командлета Get-CsCertificate, где значения параметров –Roll, -Thumbprint равны значениям строки отпечатка нового сертификата, а значение времени в параметре –EffectiveTime установлено как "07/22/2012 6:00:00 утра".</span><span class="sxs-lookup"><span data-stu-id="da4a5-161">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="da4a5-162">Он выполняет эту команду на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="da4a5-162">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="da4a5-163">![С помощью параметров рулона и EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "С помощью параметров рулона и EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="da4a5-163">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="da4a5-p115">По достижении заданного времени (7/22/2012 6:00:00 утра) все новые маркеры выпускаются новым сертификатом. Сначала выполняется проверка маркеров новым сертификатом. Если проверка не пройдена, маркеры проверяются старым сертификатом. Процедура проверки новым сертификатом и возврат к старому продолжается до тех пор, пока не истечет срок действия старого сертификата. По истечении срока действия старого сертификата (7/22/2012 14:00:00) маркеры будут проверяться только новым сертификатом. Старый сертификат можно удалить с помощью командлета Remove-CsCertificate с параметром –Previous.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p115">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="da4a5-170">Обновление и продление действия сертификата OAuthTokenIssuer с помощью параметров –Roll и -EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="da4a5-170">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="da4a5-171">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="da4a5-171">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="da4a5-172">Запросить обновление или новый сертификат OAuthTokenIssuer с экспортируемым закрытым ключом для существующего сертификата в пограничной службе аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="da4a5-172">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="da4a5-173">Импортируйте новый сертификат OAuthTokenIssuer на сервер переднего плана в пуле (при наличии развернутого пула).</span><span class="sxs-lookup"><span data-stu-id="da4a5-173">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="da4a5-174">Сертификат OAuthTokenIssuer реплицируется глобально, после чего требуется только его обновление и продление на всех серверах в текущей среде.</span><span class="sxs-lookup"><span data-stu-id="da4a5-174">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="da4a5-175">В качестве примера используется сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="da4a5-175">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="da4a5-p117">Настройте импортированный сертификат с помощью командлета Set-CsCertificate и используйте параметр –Roll вместе с параметром –EffectiveDate. Дата вступления в силу определяется как время истечения срока действия текущего сертификата (14:00:00 или 2:00:00 дня) за вычетом не менее 24 часов.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="da4a5-178">Команда Set-CsCertificate с параметрами –Roll и –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="da4a5-178">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="da4a5-179">Пример команды Set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="da4a5-179">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="da4a5-p118">Параметр EffectiveDate должен быть отформатирован в соответствии с региональными и языковыми параметрами американского английского.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="da4a5-p119">По достижении заданного времени (7/21/2012 1:00:00 ночи) все новые маркеры выпускаются новым сертификатом. Сначала выполняется проверка маркеров новым сертификатом. Если проверка не пройдена, маркеры проверяются старым сертификатом. Процедура проверки новым сертификатом и возврат к старому продолжается до тех пор, пока не истечет срок действия старого сертификата. По истечении срока действия старого сертификата (7/22/2012 14:00:00) маркеры будут проверяться только новым сертификатом. Старый сертификат можно удалить с помощью командлета Remove-CsCertificate с параметром –Previous.</span><span class="sxs-lookup"><span data-stu-id="da4a5-p119">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da4a5-188">См. также</span><span class="sxs-lookup"><span data-stu-id="da4a5-188">See Also</span></span>


[<span data-ttu-id="da4a5-189">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da4a5-189">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="da4a5-190">Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da4a5-190">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="da4a5-191">Настройка пограничных сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da4a5-191">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="da4a5-192">[Set — CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da4a5-192">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="da4a5-193">[Remove — CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da4a5-193">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

