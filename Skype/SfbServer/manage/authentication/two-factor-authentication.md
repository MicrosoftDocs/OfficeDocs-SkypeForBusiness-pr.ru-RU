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
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806548"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="c0c5f-103">Управление двух-факторной проверкой подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c0c5f-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="c0c5f-104">**Сводка:** Управление двух-факторной проверкой подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="c0c5f-105">Двух-факторная проверка подлинности обеспечивает улучшенную безопасность, требуя от пользователей предоставления двух форм проверки подлинности или идентификации, а именно сочетания имени пользователя и пароля и маркера или сертификата.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="c0c5f-106">Это также называется "что-то, что у вас есть, что-то, что вы знаете".</span><span class="sxs-lookup"><span data-stu-id="c0c5f-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="c0c5f-107">Типичным примером двух коэффициентов проверки подлинности с помощью сертификата является использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="c0c5f-108">Смарт-карта содержит сертификат, связанный с учетной записью пользователя, и может быть проверена на сведения о пользователе и сертификате, хранимые на сервере.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="c0c5f-109">Сравнивая сведения о пользователе (имя пользователя и пароль) с предоставленным сертификатом, сервер проверяет учетные данные и проверяет подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="c0c5f-110">При настройке среды Skype для бизнеса Server для поддержки двух коэффициентов проверки подлинности учитывайте следующие темы.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="c0c5f-111">Поддержка клиентов</span><span class="sxs-lookup"><span data-stu-id="c0c5f-111">Client Support</span></span>

<span data-ttu-id="c0c5f-112">Накопительные обновления для Lync Server 2013: настольный клиент за июль 2013 г. и клиент Skype для бизнеса — это единственные клиенты, которые в настоящее время поддерживают двух-факторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="c0c5f-113">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="c0c5f-113">Topology Requirements</span></span>

<span data-ttu-id="c0c5f-114">Клиентам настоятельно рекомендуется развертывать двух-факторную проверку подлинности с помощью выделенного Skype для бизнеса Server с пулами edge, Director и User Pools.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="c0c5f-115">Чтобы включить пассивную проверку подлинности для пользователей, необходимо отключить другие методы проверки подлинности для других ролей и служб, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c0c5f-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="c0c5f-116">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="c0c5f-116">**Configuration Type**</span></span>|<span data-ttu-id="c0c5f-117">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="c0c5f-117">**Service Type**</span></span>|<span data-ttu-id="c0c5f-118">**Роль сервера**</span><span class="sxs-lookup"><span data-stu-id="c0c5f-118">**Server Role**</span></span>|<span data-ttu-id="c0c5f-119">**Тип проверки подлинности для отключения**</span><span class="sxs-lookup"><span data-stu-id="c0c5f-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c0c5f-120">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="c0c5f-120">Web Service</span></span>  <br/> |<span data-ttu-id="c0c5f-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="c0c5f-121">WebServer</span></span>  <br/> |<span data-ttu-id="c0c5f-122">Директор</span><span class="sxs-lookup"><span data-stu-id="c0c5f-122">Director</span></span>  <br/> |<span data-ttu-id="c0c5f-123">Kerberos, NTLM и certificate</span><span class="sxs-lookup"><span data-stu-id="c0c5f-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="c0c5f-124">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="c0c5f-124">Web Service</span></span>  <br/> |<span data-ttu-id="c0c5f-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="c0c5f-125">WebServer</span></span>  <br/> |<span data-ttu-id="c0c5f-126">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="c0c5f-126">Front End</span></span>  <br/> |<span data-ttu-id="c0c5f-127">Kerberos, NTLM и certificate</span><span class="sxs-lookup"><span data-stu-id="c0c5f-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="c0c5f-128">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="c0c5f-128">Proxy</span></span>  <br/> |<span data-ttu-id="c0c5f-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="c0c5f-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="c0c5f-130">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c0c5f-130">Edge</span></span>  <br/> |<span data-ttu-id="c0c5f-131">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="c0c5f-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="c0c5f-132">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="c0c5f-132">Proxy</span></span>  <br/> |<span data-ttu-id="c0c5f-133">Registrar</span><span class="sxs-lookup"><span data-stu-id="c0c5f-133">Registrar</span></span>  <br/> |<span data-ttu-id="c0c5f-134">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="c0c5f-134">Front End</span></span>  <br/> |<span data-ttu-id="c0c5f-135">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="c0c5f-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="c0c5f-136">Если эти типы проверки подлинности не отключены на уровне службы, все остальные версии клиента не смогут успешно войти в нее после включения двухуровневой проверки подлинности в развертывании.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="c0c5f-137">Обнаружение служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c0c5f-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="c0c5f-138">Записи DNS, используемые внутренними и/или внешними клиентами для обнаружения служб Skype для бизнеса, должны быть настроены для разрешения на сервер Skype для бизнеса, на который не включена двух-факторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="c0c5f-139">При такой конфигурации пользователям из пулов Skype для бизнеса, не включенным для двух коэффициентов проверки подлинности, не требуется вводить ПИН-код для проверки подлинности, а пользователям из пулов Skype для бизнеса, для проверки подлинности включаемой двух коэффициентов проверки подлинности, потребуется ввести СВОЙ ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="c0c5f-140">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="c0c5f-140">Exchange Authentication</span></span>

<span data-ttu-id="c0c5f-141">Клиенты, развернувшие двух факторов проверку подлинности для Microsoft Exchange, могут обнаружить, что некоторые функции клиента недоступны.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="c0c5f-142">В настоящее время такая проверка подлинности не поддерживается, так как клиент Skype для бизнеса не поддерживает двух-факторную проверку подлинности для функций, зависящих от интеграции Exchange.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="c0c5f-143">Контакты</span><span class="sxs-lookup"><span data-stu-id="c0c5f-143">Contacts</span></span>

<span data-ttu-id="c0c5f-144">Пользователи Skype для бизнеса, настроенные на использование функции единого магазина контактов, поймят, что их контакты больше недоступны после того, как войдите в систему с помощью двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="c0c5f-145">Для удаления существующих пользовательских контактов из единого магазина контактов и их хранения в Skype для бизнеса Server перед включением двух коэффициентов проверки подлинности следует использовать для этого **cmdlet Invoke-CsUcsRollback.**</span><span class="sxs-lookup"><span data-stu-id="c0c5f-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="c0c5f-146">Поиск по навыкам</span><span class="sxs-lookup"><span data-stu-id="c0c5f-146">Skill Search</span></span>

<span data-ttu-id="c0c5f-147">Пользователи, настроившие функцию поиска по навыкам в своей среде Skype для бизнеса, поймят, что эта функция не работает, если в Skype для бизнеса включена двух коэффициентовая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="c0c5f-148">Это так, так как Microsoft SharePoint в настоящее время не поддерживает двухзначную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="c0c5f-149">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="c0c5f-149">Credentials</span></span>

<span data-ttu-id="c0c5f-150">Существует ряд аспектов развертывания, связанных с сохраненными учетными данными Skype для бизнеса, которые могут повлиять на пользователей, настроенных на использование двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="c0c5f-151">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="c0c5f-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="c0c5f-152">Пользователи должны  использовать параметр "Удалить мои данные для регистрации" в клиенте Skype для бизнеса и удалить свою папку профиля SIP из папки %localappdata%\Microsoft\Office\15.0\Skype для бизнеса перед первой попыткой подписаться с помощью двух коэффициентов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="c0c5f-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="c0c5f-153">DisableNTCredentials</span></span>

<span data-ttu-id="c0c5f-154">С помощью метода проверки подлинности Kerberos или NTLM учетные данные windows пользователя автоматически используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="c0c5f-155">В типичном развертывании Skype для бизнеса Server, где проверка подлинности Kerberos и/или NTLM включена, пользователям не нужно вводить свои учетные данные при каждом входе.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="c0c5f-156">Если пользователи непреднамеренно запросят учетные данные перед вводом ПИН-кода, то на клиентских компьютерах может быть непреднамеренно настроен ключ реестра **DisableNTCredentials,** возможно, с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="c0c5f-157">Чтобы запретить дополнительные запросы учетных данных, создайте следующую запись реестра на локальной рабочей станции или используйте административный шаблон Skype для бизнеса, чтобы применить его для всех пользователей заданного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="c0c5f-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="c0c5f-158">Сохранение пароля</span><span class="sxs-lookup"><span data-stu-id="c0c5f-158">SavePassword</span></span>

<span data-ttu-id="c0c5f-159">Когда пользователь впервые вошел в Skype для бизнеса, ему будет предложено сохранить свой пароль.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="c0c5f-160">Если этот параметр выбран, клиентский сертификат пользователя можно хранить в личном хранилище сертификатов, а учетные данные Windows пользователя — в диспетчере учетных данных локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="c0c5f-161">Параметр **реестра SavePassword** должен быть отключен, если в Skype для бизнеса настроена поддержка двух факторов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="c0c5f-162">Чтобы запретить пользователям сохранять пароли, измените следующую запись реестра на локальной рабочей станции или используйте административный шаблон Skype для бизнеса, чтобы применить его к всем пользователям для заданного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="c0c5f-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="c0c5f-163">Воспроизведение маркеров AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="c0c5f-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="c0c5f-164">AD FS 2.0 предоставляет функцию, которая называется обнаружением повтора маркеров, с помощью которой можно обнаруживать и отклоняя несколько запросов маркеров с использованием одного маркера.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="c0c5f-165">Если эта функция включена, обнаружение повтора маркеров защищает целостность запросов проверки подлинности как в пассивном профиле WS-Federation, так и в профиле SAML WebSSO, убедившись, что один и тот же маркер не используется более одного раза.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="c0c5f-166">Эту функцию следует включить в тех случаях, когда безопасность очень высока, например при использовании терминалов.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="c0c5f-167">Дополнительные сведения об обнаружении повтора маркеров см. в дополнительных сведениях о планировании и развертывании [AD FS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=309215)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="c0c5f-168">Доступ внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="c0c5f-168">External User Access</span></span>

<span data-ttu-id="c0c5f-169">Настройка прокси-сервера ADFS или обратного прокси-сервера для поддержки двух коэффициентов проверки подлинности Skype для бизнеса из внешних сетей не освещается в этих темах.</span><span class="sxs-lookup"><span data-stu-id="c0c5f-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0c5f-170">См. также</span><span class="sxs-lookup"><span data-stu-id="c0c5f-170">See also</span></span>

[<span data-ttu-id="c0c5f-171">Настройка двух коэффициентов проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c0c5f-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
