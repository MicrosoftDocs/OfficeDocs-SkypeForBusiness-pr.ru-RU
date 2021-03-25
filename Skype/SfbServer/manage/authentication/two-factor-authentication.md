---
title: Управление двух-факторной проверкой подлинности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: Сводка. Управление двух-факторной проверкой подлинности в Skype для бизнеса Server.
ms.openlocfilehash: 8e8f665d824cd5f21cc2ca874668eba90bc97c4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119548"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="621d1-103">Управление двух-факторной проверкой подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="621d1-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="621d1-104">**Сводка:** Управление двух-факторной проверкой подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="621d1-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="621d1-105">Двух факторов проверки подлинности обеспечивает улучшенную безопасность, требуя от пользователей предоставить две формы проверки подлинности или идентификации, а именно сочетание имени пользователя и пароля и маркера или сертификата.</span><span class="sxs-lookup"><span data-stu-id="621d1-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="621d1-106">Это также называется "что-то у вас есть, то, что вы знаете".</span><span class="sxs-lookup"><span data-stu-id="621d1-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="621d1-107">Типичным примером двух факторов проверки подлинности с сертификатом является использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="621d1-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="621d1-108">Смарт-карта содержит сертификат, связанный с учетной записью пользователя, и может быть проверена на основе сведений о пользователях и сертификатах, хранимых на сервере.</span><span class="sxs-lookup"><span data-stu-id="621d1-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="621d1-109">Сравнивая данные пользователя (имя пользователя и пароль) с предоставленным сертификатом, сервер проверяет учетные данные и проверяет подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="621d1-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="621d1-110">Рассмотрим следующие темы при настройке среды Skype для бизнес-сервера для поддержки двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="621d1-111">Поддержка клиентов</span><span class="sxs-lookup"><span data-stu-id="621d1-111">Client Support</span></span>

<span data-ttu-id="621d1-112">Накопительные обновления для настольного клиента Lync Server 2013: июль 2013 г. и клиент Skype для бизнеса являются единственными клиентами, которые в настоящее время поддерживают двух факторов проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="621d1-113">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="621d1-113">Topology Requirements</span></span>

<span data-ttu-id="621d1-114">Настоятельно рекомендуется развертывать двух факторов проверку подлинности с помощью выделенных Skype для бизнес-сервера с помощью пулов edge, Director и User Pools.</span><span class="sxs-lookup"><span data-stu-id="621d1-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="621d1-115">Чтобы включить пассивную проверку подлинности для пользователей, другие методы проверки подлинности должны быть отключены для других ролей и служб, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="621d1-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="621d1-116">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="621d1-116">**Configuration Type**</span></span>|<span data-ttu-id="621d1-117">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="621d1-117">**Service Type**</span></span>|<span data-ttu-id="621d1-118">**Роль сервера**</span><span class="sxs-lookup"><span data-stu-id="621d1-118">**Server Role**</span></span>|<span data-ttu-id="621d1-119">**Тип проверки подлинности для отключения**</span><span class="sxs-lookup"><span data-stu-id="621d1-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="621d1-120">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="621d1-120">Web Service</span></span>  <br/> |<span data-ttu-id="621d1-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="621d1-121">WebServer</span></span>  <br/> |<span data-ttu-id="621d1-122">Директор</span><span class="sxs-lookup"><span data-stu-id="621d1-122">Director</span></span>  <br/> |<span data-ttu-id="621d1-123">Kerberos, NTLM и Certificate</span><span class="sxs-lookup"><span data-stu-id="621d1-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="621d1-124">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="621d1-124">Web Service</span></span>  <br/> |<span data-ttu-id="621d1-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="621d1-125">WebServer</span></span>  <br/> |<span data-ttu-id="621d1-126">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="621d1-126">Front End</span></span>  <br/> |<span data-ttu-id="621d1-127">Kerberos, NTLM и Certificate</span><span class="sxs-lookup"><span data-stu-id="621d1-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="621d1-128">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="621d1-128">Proxy</span></span>  <br/> |<span data-ttu-id="621d1-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="621d1-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="621d1-130">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="621d1-130">Edge</span></span>  <br/> |<span data-ttu-id="621d1-131">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="621d1-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="621d1-132">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="621d1-132">Proxy</span></span>  <br/> |<span data-ttu-id="621d1-133">Регистратор</span><span class="sxs-lookup"><span data-stu-id="621d1-133">Registrar</span></span>  <br/> |<span data-ttu-id="621d1-134">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="621d1-134">Front End</span></span>  <br/> |<span data-ttu-id="621d1-135">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="621d1-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="621d1-136">Если эти типы проверки подлинности не отключены на уровне службы, все другие версии клиента не смогут успешно войти после включения двух факторов проверки подлинности в развертывании.</span><span class="sxs-lookup"><span data-stu-id="621d1-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="621d1-137">Обнаружение служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="621d1-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="621d1-138">Записи DNS, используемые внутренними и/или внешними клиентами для обнаружения служб Skype для бизнеса, должны быть настроены для разрешения на сервер Skype для бизнеса, который не включен для двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="621d1-139">При такой конфигурации пользователям из пулов Skype для бизнеса, не включенным для двух факторов проверки подлинности, не потребуется вводить ПИН-код для проверки подлинности, а пользователям из пулов Skype для бизнеса, которые включены для двух факторов проверки подлинности, потребуется ввести ПИН-код для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="621d1-140">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="621d1-140">Exchange Authentication</span></span>

<span data-ttu-id="621d1-141">Клиенты, развернувшие двух факторов проверку подлинности для Microsoft Exchange, могут обнаружить, что некоторые функции в клиенте недоступны.</span><span class="sxs-lookup"><span data-stu-id="621d1-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="621d1-142">В настоящее время это происходит по проекту, так как клиент Skype для бизнеса не поддерживает двух факторов проверку подлинности для функций, зависящих от интеграции Exchange.</span><span class="sxs-lookup"><span data-stu-id="621d1-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="621d1-143">Контакты</span><span class="sxs-lookup"><span data-stu-id="621d1-143">Contacts</span></span>

<span data-ttu-id="621d1-144">Пользователи Skype для бизнеса, настроенные для использования функции Единого магазина контактов, поймят, что их контакты больше не доступны после регистрации с помощью двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="621d1-145">Чтобы удалить существующие контакты пользователей из Единого магазина контактов и хранить их в Skype для бизнеса Server, прежде чем включите двух факторов проверку подлинности, следует использовать с помощью **cmdlet Invoke-CsUcsRollback.**</span><span class="sxs-lookup"><span data-stu-id="621d1-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="621d1-146">Поиск навыков</span><span class="sxs-lookup"><span data-stu-id="621d1-146">Skill Search</span></span>

<span data-ttu-id="621d1-147">Клиенты, которые настроили функцию поиска навыков в среде Skype для бизнеса, будут находить, что эта функция не работает, когда Skype для бизнеса включен для двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="621d1-148">Это происходит по проекту, так как Microsoft SharePoint в настоящее время не поддерживает двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="621d1-149">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="621d1-149">Credentials</span></span>

<span data-ttu-id="621d1-150">Существует ряд аспектов развертывания, связанных с сохраненными учетными данными Skype для бизнеса, которые могут повлиять на пользователей, настроенных на использование двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="621d1-151">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="621d1-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="621d1-152">Пользователи должны использовать параметр Delete **my sign-in info** в клиенте Skype для бизнеса и удалить папку профилей SIP из %localappdata%\Microsoft\Office\15.0\Skype для бизнеса, прежде чем пытаться подписаться впервые с помощью двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="621d1-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="621d1-153">DisableNTCredentials</span></span>

<span data-ttu-id="621d1-154">С помощью метода проверки подлинности Kerberos или NTLM учетные данные windows пользователя автоматически используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="621d1-155">В типичном развертывании Skype для бизнес-сервера, где kerberos и/или NTLM включены для проверки подлинности, пользователям не следует вводить учетные данные при каждом входе.</span><span class="sxs-lookup"><span data-stu-id="621d1-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="621d1-156">Если пользователи непреднамеренно запросили учетные данные перед вводом ПИН-кода, ключ реестра **DisableNTCredentials** может быть непреднамеренно настроен на клиентских компьютерах, возможно, с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="621d1-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="621d1-157">Чтобы предотвратить дополнительную подсказку для учетных данных, создайте следующую запись реестра на локальной рабочей станции или используйте административный шаблон Skype для бизнеса, чтобы примениться к всем пользователям для данного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="621d1-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="621d1-158">Сохранение пароля</span><span class="sxs-lookup"><span data-stu-id="621d1-158">SavePassword</span></span>

<span data-ttu-id="621d1-159">Когда пользователь впервые вошел в Skype для бизнеса, ему будет предложено сохранить пароль.</span><span class="sxs-lookup"><span data-stu-id="621d1-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="621d1-160">При выборе этот параметр позволяет хранить клиентский сертификат пользователя в личном хранилище сертификатов, а учетные данные пользователя с Windows храниться в диспетчере учетных данных локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="621d1-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="621d1-161">Параметр **реестра SavePassword** должен быть отключен при настройке Skype для бизнеса для поддержки двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="621d1-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="621d1-162">Чтобы предотвратить сохранение паролей пользователями, измените следующую запись реестра на локальной рабочей станции или используйте административный шаблон Skype для бизнеса, чтобы примениться к всем пользователям для данного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="621d1-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="621d1-163">Повтор маркеров AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="621d1-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="621d1-164">AD FS 2.0 предоставляет функцию, именуемую обнаружением повтора маркеров, с помощью которой можно обнаружить несколько запросов маркеров с помощью одного маркера, а затем отменить их.</span><span class="sxs-lookup"><span data-stu-id="621d1-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="621d1-165">Если эта функция включена, обнаружение повторов маркеров защищает целостность запросов на проверку подлинности как в пассивном профиле WS-Federation, так и в профиле SAML WebSSO, убедившись, что один и тот же маркер никогда не используется более одного раза.</span><span class="sxs-lookup"><span data-stu-id="621d1-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="621d1-166">Эта функция должна быть включена в ситуациях, когда безопасность является очень высокой проблемой, например при использовании киосков.</span><span class="sxs-lookup"><span data-stu-id="621d1-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="621d1-167">Дополнительные сведения об обнаружении повторов маркеров см. в дополнительных сведениях о практике безопасного планирования и развертывания [AD FS 2.0.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="621d1-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="621d1-168">Внешний доступ к пользователю</span><span class="sxs-lookup"><span data-stu-id="621d1-168">External User Access</span></span>

<span data-ttu-id="621d1-169">Настройка прокси-сервера ADFS или обратного прокси-сервера для поддержки двух факторов проверки подлинности Skype для бизнеса из внешних сетей не освещается в этих темах.</span><span class="sxs-lookup"><span data-stu-id="621d1-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="621d1-170">См. также</span><span class="sxs-lookup"><span data-stu-id="621d1-170">See also</span></span>

[<span data-ttu-id="621d1-171">Настройка двух факторов проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="621d1-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
