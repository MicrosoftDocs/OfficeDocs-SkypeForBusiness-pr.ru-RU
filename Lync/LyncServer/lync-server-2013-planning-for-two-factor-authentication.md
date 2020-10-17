---
title: 'Lync Server 2013: планирование двухфакторной проверки подлинности'
description: 'Lync Server 2013: планирование двухфакторной проверки подлинности.'
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
ms.openlocfilehash: 6a3a2cd5508f6ce9a8a389b0059a09747b9f9a09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564005"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="b6ba8-103">Планирование двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6ba8-103">Planning for two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6ba8-104">_**Последнее изменение темы:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="b6ba8-104">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="b6ba8-105">Ниже приведен список рекомендаций по развертыванию при настройке среды Microsoft Lync Server 2013 для поддержки двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-105">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="b6ba8-106">Поддержка клиентов</span><span class="sxs-lookup"><span data-stu-id="b6ba8-106">Client Support</span></span>

<span data-ttu-id="b6ba8-107">Накопительные пакеты обновления для Lync 2013 для Lync Server 2013: Июль 2013 клиент для настольных ПК и все мобильные клиенты в настоящее время поддерживают двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-107">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="b6ba8-108">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="b6ba8-108">Topology Requirements</span></span>

<span data-ttu-id="b6ba8-109">Пользователям настоятельно рекомендуется развертывать двухфакторную проверку подлинности с помощью выделенного сервера Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: Июль 2013 EDGE, Director и пулы пользователей.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-109">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="b6ba8-110">Чтобы включить пассивную проверку подлинности для пользователей Lync, другие методы проверки подлинности должны быть отключены для других ролей и служб, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="b6ba8-110">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6ba8-111">Тип конфигурации</span><span class="sxs-lookup"><span data-stu-id="b6ba8-111">Configuration Type</span></span></th>
<th><span data-ttu-id="b6ba8-112">Тип службы</span><span class="sxs-lookup"><span data-stu-id="b6ba8-112">Service Type</span></span></th>
<th><span data-ttu-id="b6ba8-113">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="b6ba8-113">Server Role</span></span></th>
<th><span data-ttu-id="b6ba8-114">Тип проверки подлинности для отключения</span><span class="sxs-lookup"><span data-stu-id="b6ba8-114">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6ba8-115">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="b6ba8-115">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-116">WebServer</span><span class="sxs-lookup"><span data-stu-id="b6ba8-116">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-117">Директор</span><span class="sxs-lookup"><span data-stu-id="b6ba8-117">Director</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-118">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="b6ba8-118">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ba8-119">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="b6ba8-119">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-120">WebServer</span><span class="sxs-lookup"><span data-stu-id="b6ba8-120">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-121">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="b6ba8-121">Front End</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-122">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="b6ba8-122">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ba8-123">Сервера</span><span class="sxs-lookup"><span data-stu-id="b6ba8-123">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-124">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b6ba8-124">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-125">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b6ba8-125">Edge</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-126">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="b6ba8-126">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ba8-127">Сервера</span><span class="sxs-lookup"><span data-stu-id="b6ba8-127">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-128">Регистратор</span><span class="sxs-lookup"><span data-stu-id="b6ba8-128">Registrar</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-129">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="b6ba8-129">Front End</span></span></p></td>
<td><p><span data-ttu-id="b6ba8-130">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="b6ba8-130">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b6ba8-131">Если эти типы проверки подлинности не отключены на уровне службы, во всех остальных версиях клиента Lync не удастся выполнить вход в систему после включения двухфакторной проверки подлинности в пределах развертывания.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-131">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="b6ba8-132">Обнаружение службы Lync</span><span class="sxs-lookup"><span data-stu-id="b6ba8-132">Lync Service Discovery</span></span>

<span data-ttu-id="b6ba8-133">Записи DNS, используемые внутренними и/или внешними клиентами для обнаружения служб Lync, должны быть настроены для разрешения на сервер Lync, для которого не включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-133">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="b6ba8-134">В этой конфигурации пользователи из пулов Lync, для которых не включена двухфакторная проверка подлинности, не должны вводить ПИН-код для проверки подлинности, а пользователи из пулов Lync, для которых включена двухфакторная проверка подлинности, должны ввести свой ПИН-код для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-134">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="b6ba8-135">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="b6ba8-135">Exchange Authentication</span></span>

<span data-ttu-id="b6ba8-136">Клиенты, которые развернули двухфакторную проверку подлинности для Microsoft Exchange, могут обнаружить, что некоторые функции в клиенте Lync недоступны.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-136">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="b6ba8-137">В настоящее время он разрабатывается, так как клиент Lync не поддерживает двухфакторную проверку подлинности для функций, зависящих от интеграции Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-137">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="b6ba8-138">Контакты Lync</span><span class="sxs-lookup"><span data-stu-id="b6ba8-138">Lync Contacts</span></span>

<span data-ttu-id="b6ba8-139">Пользователи Lync, которые настроены для использования единой функции хранилища контактов, смогут обнаружить, что их контакты больше не будут доступны после входа с использованием двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-139">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="b6ba8-140">Следует использовать командлет **Invoke – CsUcsRollback** для удаления существующих контактов пользователей из единого хранилища контактов и их хранения в Lync Server 2013 перед включением двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-140">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="b6ba8-141">Поиск по навыкам</span><span class="sxs-lookup"><span data-stu-id="b6ba8-141">Skill Search</span></span>

<span data-ttu-id="b6ba8-142">Пользователи, которые настроили функцию поиска по навыкам в среде Lync, смогут обнаружить, что эта функция не работает, если для Lync включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-142">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="b6ba8-143">Это сделано намеренно, так как Microsoft SharePoint в настоящее время не поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-143">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="b6ba8-144">Учетные данные Lync</span><span class="sxs-lookup"><span data-stu-id="b6ba8-144">Lync Credentials</span></span>

<span data-ttu-id="b6ba8-145">Существует ряд вопросов, связанных с развертыванием учетных данных Lync, которые могут повлиять на пользователей, использующих двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-145">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="b6ba8-146">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="b6ba8-146">Deleting Saved Credentials</span></span>

<span data-ttu-id="b6ba8-147">Пользователи настольного клиента должны использовать параметр " **удалить сведения о входе в систему** " в клиенте Lync и удалять свою папку профиля SIP из% локалаппдата% \\ Microsoft \\ Office \\ 15,0 \\ Lync, прежде чем пытаться войти в первый раз с использованием двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-147">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="b6ba8-148">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b6ba8-148">DisableNTCredentials</span></span>

<span data-ttu-id="b6ba8-149">При использовании метода проверки подлинности Kerberos или NTLM учетные данные пользователя Windows используются автоматически для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-149">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="b6ba8-150">В типичном развертывании Lync Server 2013, где для проверки подлинности включена проверка подлинности Kerberos и/или NTLM, пользователям не придется вводить свои учетные данные при каждом входе в систему.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-150">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="b6ba8-151">Если пользователям непреднамеренно запрашиваются учетные данные, прежде чем им будет предложено ввести ПИН-код, раздел реестра **DisableNTCredentials** может быть непреднамеренно настроен на клиентских компьютерах, возможно, с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-151">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="b6ba8-152">Чтобы не допустить дополнительных запросов учетных данных, создайте следующую запись реестра на локальной рабочей станции или используйте административный шаблон Lync для применения ко всем пользователям для определенного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="b6ba8-152">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b6ba8-153">\_Локальные \_ \\ политики программного обеспечения для локального компьютера, \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="b6ba8-153">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b6ba8-154">REG \_ DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b6ba8-154">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="b6ba8-155">Значение: 0x0</span><span class="sxs-lookup"><span data-stu-id="b6ba8-155">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="b6ba8-156">Сохранение пароля</span><span class="sxs-lookup"><span data-stu-id="b6ba8-156">SavePassword</span></span>

<span data-ttu-id="b6ba8-157">Когда пользователь первый раз выполняет вход в Lync, пользователю предлагается сохранить пароль.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-157">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="b6ba8-158">Если этот параметр выбран, этот параметр позволяет хранить сертификат клиента пользователя в хранилище личных сертификатов, а учетные данные пользователя Windows для хранения в диспетчере учетных данных локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-158">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="b6ba8-159">Параметр реестра **SavePassword** должен быть отключен при настройке Lync для поддержки двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-159">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="b6ba8-160">Чтобы запретить пользователям сохранять свои пароли, измените следующую запись реестра на локальной рабочей станции или используйте административный шаблон Lync для применения ко всем пользователям для определенного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="b6ba8-160">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b6ba8-161">\_ \_ Программное обеспечение для текущего пользователя hKey \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="b6ba8-161">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b6ba8-162">REG \_ DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="b6ba8-162">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="b6ba8-163">Значение: 0x0</span><span class="sxs-lookup"><span data-stu-id="b6ba8-163">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="b6ba8-164">Повторный запуск маркеров AD FS 2,0</span><span class="sxs-lookup"><span data-stu-id="b6ba8-164">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="b6ba8-165">AD FS 2,0 предоставляет функцию обнаружения повторяющихся маркеров, с помощью которой можно обнаружить несколько запросов маркеров, использующих один и тот же маркер, а затем удалить их.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-165">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="b6ba8-166">Если эта функция включена, обнаружение повторяющихся маркеров защищает целостность запросов проверки подлинности в пассивном профиле WS-Federation и в профиле SAML Вебссо, убедившись, что один и тот же маркер никогда не использовался более одного раза.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-166">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="b6ba8-167">Эту функцию следует включать в тех случаях, когда безопасность очень важна, например, при использовании киосков.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-167">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="b6ba8-168">Дополнительные сведения об обнаружении повторяющихся маркеров приведены в разделе рекомендации по обеспечению безопасного планирования и развертыванию служб федерации Active Directory 2,0 по адресу [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) .</span><span class="sxs-lookup"><span data-stu-id="b6ba8-168">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="b6ba8-169">Доступ внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="b6ba8-169">External User Access</span></span>

<span data-ttu-id="b6ba8-170">Настройка прокси-сервера AD FS или обратного прокси-сервера для поддержки двухфакторной проверки подлинности Lync из внешних сетей не рассматривается в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-170">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

