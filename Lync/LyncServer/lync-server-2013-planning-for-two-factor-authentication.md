---
title: 'Lync Server 2013: планирование двухфакторной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="1f910-102">Планирование двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f910-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f910-103">_**Тема последнего изменения:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="1f910-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="1f910-104">Ниже приведен список вопросов развертывания при настройке среды Microsoft Lync Server 2013 для поддержки двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="1f910-105">Поддержка клиента</span><span class="sxs-lookup"><span data-stu-id="1f910-105">Client Support</span></span>

<span data-ttu-id="1f910-106">Накопительные обновления Lync 2013 для Lync Server 2013: Июль 2013 клиентскую версию для настольных компьютеров и все мобильные клиенты, которые в настоящее время поддерживают двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="1f910-107">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="1f910-107">Topology Requirements</span></span>

<span data-ttu-id="1f910-108">Пользователям настоятельно рекомендуется развернуть двухфакторную проверку подлинности с помощью выделенного сервера Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Июль 2013 EDGE, режиссер и пулы пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f910-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="1f910-109">Чтобы включить пассивную проверку подлинности для пользователей Lync, другие методы проверки подлинности должны быть отключены для других ролей и служб, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="1f910-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f910-110">Тип конфигурации</span><span class="sxs-lookup"><span data-stu-id="1f910-110">Configuration Type</span></span></th>
<th><span data-ttu-id="1f910-111">Тип службы</span><span class="sxs-lookup"><span data-stu-id="1f910-111">Service Type</span></span></th>
<th><span data-ttu-id="1f910-112">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="1f910-112">Server Role</span></span></th>
<th><span data-ttu-id="1f910-113">Тип проверки подлинности, который нужно отключить</span><span class="sxs-lookup"><span data-stu-id="1f910-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f910-114">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="1f910-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1f910-115">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="1f910-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1f910-116">Директор</span><span class="sxs-lookup"><span data-stu-id="1f910-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1f910-117">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="1f910-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f910-118">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="1f910-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1f910-119">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="1f910-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1f910-120">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1f910-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="1f910-121">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="1f910-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f910-122">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1f910-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1f910-123">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="1f910-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="1f910-124">Пограничный</span><span class="sxs-lookup"><span data-stu-id="1f910-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="1f910-125">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="1f910-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f910-126">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1f910-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1f910-127">Регистратор</span><span class="sxs-lookup"><span data-stu-id="1f910-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="1f910-128">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1f910-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="1f910-129">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="1f910-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f910-130">Если эти типы проверки подлинности не отключены на уровне обслуживания, во всех остальных версиях клиента Lync после включения двухфакторной проверки подлинности в рамках развертывания будет невозможно выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="1f910-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="1f910-131">Обнаружение служб Lync</span><span class="sxs-lookup"><span data-stu-id="1f910-131">Lync Service Discovery</span></span>

<span data-ttu-id="1f910-132">DNS-записи, используемые внутренними и внешними клиентами для поиска служб Lync, должны быть настроены для разрешения на доступ к серверу Lync Server, для которого не включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="1f910-133">В этой конфигурации пользователи из пулов Lync, для которых не включена двухфакторная проверка подлинности, не должны вводить PIN-код для проверки подлинности, а пользователи из пулов Lync, поддерживающих двухфакторную проверку подлинности, должны вводить PIN-код. выполняться.</span><span class="sxs-lookup"><span data-stu-id="1f910-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="1f910-134">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="1f910-134">Exchange Authentication</span></span>

<span data-ttu-id="1f910-135">Пользователи, которые развернули двухфакторную проверку подлинности для Microsoft Exchange, могут обнаружить, что некоторые функции в клиенте Lync недоступны.</span><span class="sxs-lookup"><span data-stu-id="1f910-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="1f910-136">В настоящее время это дизайн, так как клиент Lync не поддерживает двухфакторную проверку подлинности для функций, которые зависят от интеграции Exchange.</span><span class="sxs-lookup"><span data-stu-id="1f910-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="1f910-137">Контакты Lync</span><span class="sxs-lookup"><span data-stu-id="1f910-137">Lync Contacts</span></span>

<span data-ttu-id="1f910-138">Пользователи Lync, которые настроены на использование единой функции магазина контактов, смогут обнаружить, что их контакты больше не будут доступны после входа с помощью двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="1f910-139">Для удаления существующих контактов пользователей из единого хранилища контактов и их хранения в Lync Server 2013 перед включением двухфакторной проверки подлинности следует использовать командлет **Invoke-ксуксроллбакк** .</span><span class="sxs-lookup"><span data-stu-id="1f910-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="1f910-140">Поиск по навыкам</span><span class="sxs-lookup"><span data-stu-id="1f910-140">Skill Search</span></span>

<span data-ttu-id="1f910-141">Пользователи, которые настроили функцию поиска по навыкам в среде Lync, найдут, что эта функция не работает, если в Lync включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="1f910-142">Это объясняется тем, что Microsoft SharePoint не поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="1f910-143">Учетные данные Lync</span><span class="sxs-lookup"><span data-stu-id="1f910-143">Lync Credentials</span></span>

<span data-ttu-id="1f910-144">Существует ряд вопросов по развертыванию с использованием сохраненных учетных данных Lync, которые могут повлиять на пользователей, которые настроены на использование двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="1f910-145">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="1f910-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="1f910-146">Пользователи настольного клиента должны использовать параметр " **удалить мои данные для входа** " в клиенте Lync и удалить папку профиля SIP из% LocalAppData\\%\\Microsoft\\Office\\15,0 Lync, прежде чем пытаться зарегистрироваться в первый раз с помощью двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="1f910-147">Отключение учетных данных NTC</span><span class="sxs-lookup"><span data-stu-id="1f910-147">DisableNTCredentials</span></span>

<span data-ttu-id="1f910-148">При использовании способа проверки подлинности Kerberos или NTLM автоматически применяются учетные данные пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="1f910-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="1f910-149">В типичном развертывании Lync Server 2013 там, где для проверки подлинности используется протокол Kerberos и (или) NTLM, пользователи не должны вводить свои учетные данные при каждом входе.</span><span class="sxs-lookup"><span data-stu-id="1f910-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="1f910-150">Если у пользователя запрашиваются учетные данные перед появлением запроса ПИН-кода, на клиентском компьютере мог быть случайно настроен раздел реестра **DisableNTCredentials** (возможно, через групповую политику).</span><span class="sxs-lookup"><span data-stu-id="1f910-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="1f910-151">Чтобы не допустить дополнительных запросов на ввод учетных данных, создайте на локальной рабочей станции следующий параметр реестра или используйте административный шаблон Lync, чтобы применить ко всем пользователям для определенного пула с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="1f910-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1f910-152">Политики\_\\программного\\обеспечения\\для локального\_компьютера\\(\\hKey) Microsoft\\Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="1f910-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1f910-153">REG\_DWORD: дисабленткредентиалс</span><span class="sxs-lookup"><span data-stu-id="1f910-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="1f910-154">Значение: 0x0</span><span class="sxs-lookup"><span data-stu-id="1f910-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="1f910-155">Сохранение пароля</span><span class="sxs-lookup"><span data-stu-id="1f910-155">SavePassword</span></span>

<span data-ttu-id="1f910-156">При первом входе пользователя в Lync пользователю будет предложено сохранить свой пароль.</span><span class="sxs-lookup"><span data-stu-id="1f910-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="1f910-157">Это позволит пользователю сохранить свой сертификат клиента в хранилище личных сертификатов, а учетные данные Windows — в диспетчере учетных данных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1f910-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="1f910-158">Параметр реестра **савепассворд** должен быть отключен, если в Lync настроена поддержка двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1f910-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="1f910-159">Чтобы запретить пользователям сохранять пароли, измените следующий параметр реестра на локальной рабочей станции или используйте административный шаблон Lync, чтобы применить ко всем пользователям для определенного пула с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="1f910-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1f910-160">Программа\_\\hKey\_для\\текущего пользователя\\,\\Microsoft\\Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="1f910-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1f910-161">REG\_DWORD: савепассворд</span><span class="sxs-lookup"><span data-stu-id="1f910-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="1f910-162">Значение: 0x0</span><span class="sxs-lookup"><span data-stu-id="1f910-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="1f910-163">Повтор маркера AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="1f910-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="1f910-p108">AD FS 2.0 обеспечивает функцию обнаружения повтора маркера, которая позволяет обнаружить и отменить ряд запросов, использующих один маркер. Эта функция поддерживает целостность запросов проверки подлинности в пассивном профиле федерации веб-служб и профиле SAML WebSSO, не позволяя использовать один маркер несколько раз.</span><span class="sxs-lookup"><span data-stu-id="1f910-p108">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="1f910-166">Функция обнаружения повтора маркера необходима в особо опасных условиях, например в интерактивных терминалах.</span><span class="sxs-lookup"><span data-stu-id="1f910-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="1f910-167">Дополнительные сведения об определении воспроизведении маркеров можно найти в разделе Советы и рекомендации по обеспечению безопасности при планировании [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)и развертывании AD FS 2,0 по адресу.</span><span class="sxs-lookup"><span data-stu-id="1f910-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="1f910-168">Доступ внешнего пользователя</span><span class="sxs-lookup"><span data-stu-id="1f910-168">External User Access</span></span>

<span data-ttu-id="1f910-169">Настройка прокси-сервера AD FS или обратного прокси-сервера для поддержки двухфакторной проверки подлинности Lync из внешних сетей не рассматривается в указанных ниже разделах.</span><span class="sxs-lookup"><span data-stu-id="1f910-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

