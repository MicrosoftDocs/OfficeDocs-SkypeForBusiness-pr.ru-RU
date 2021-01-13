---
title: Планирование современной проверки подлинности в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Разделы по планированию проверки подлинности и авторизации для Skype для бизнеса Server, включая интеграцию с другими продуктами
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816249"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="b93d4-103">Обсуждение проверки подлинности и авторизации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b93d4-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="b93d4-104">Проверка подлинности и авторизация — это связанные понятия, но вы можете работать по-разному (хотя они и необходимы).</span><span class="sxs-lookup"><span data-stu-id="b93d4-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="b93d4-105">Другими словами, аутентиниция (AuthN) зависит от секретов, которые знает или имеет только действительный пользователь, который может быть паролем, кодом, отпечатком пальца, сертификатом, комбинацией утверждений о пользователе, которые являются истинными, или сочетанием этих утверждений, используемых вместе.</span><span class="sxs-lookup"><span data-stu-id="b93d4-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="b93d4-106">AuthN — это процесс, который подтверждает свою правота.</span><span class="sxs-lookup"><span data-stu-id="b93d4-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="b93d4-107">Авторизация (AuthZ) касается того, к чему у вас есть доступ после того, как вы доказывали, кто вы есть.</span><span class="sxs-lookup"><span data-stu-id="b93d4-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="b93d4-108">Он определяет, что вам было разрешено видеть, редактировать и по-другому получать доступ.</span><span class="sxs-lookup"><span data-stu-id="b93d4-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="b93d4-109">Например, у вас может быть мощный доступ администратора к SharePoint Online, но если вы переключитесь на другую нагрузку в Интернете, например Skype для бизнеса Online, у вас могут быть права на устранение неполадок пользователей, а не на изменение конфигурации сервера или серверов.</span><span class="sxs-lookup"><span data-stu-id="b93d4-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="b93d4-110">В третьей рабочей нагрузке, например Exchange Online, у вас может быть доступ только среднего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b93d4-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="b93d4-111">AuthZ проверяет, какой и какой объем доступа у вас есть к службам/worloads, приложениям, файлам и другим данным.</span><span class="sxs-lookup"><span data-stu-id="b93d4-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="b93d4-112">В наших примерах включаются сетевые свойства, такие как SharePoint и Exchange Online, но процессы AuthN и AuthZ работают в локальной и гибридной локальной системах одинаково.</span><span class="sxs-lookup"><span data-stu-id="b93d4-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="b93d4-113">В конечном счете такие средства, как AAD Connect и ADFS, становятся частью истории AuthN и AuthZ путем синхронизации учетных записей и паролей в облачной службе AD (azure AD) или вторжением в поток AuthZ, чтобы пользователь не часто запросил свои учетные данные, например при переключении между рабочими нагрузками в облаке, создавая сценарии single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b93d4-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="b93d4-114">Но они сами по себе не являются частью механизмов authN или AuthZ.</span><span class="sxs-lookup"><span data-stu-id="b93d4-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="b93d4-115">Сегодня многие технологии считают эти процессы (AuthN и AuthZ) одним из механизмов, и вы услышите множество ссылок на процесс проверки подлинности, которые также включают в себя авторизацию.</span><span class="sxs-lookup"><span data-stu-id="b93d4-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="b93d4-116">Важно помнить, что первым шагом в доступе пользователей является AuthN, доказав, что вы действительно действительно и что AuthZ использует знания о том, к кому пользователь имеет доступ (как вы увидите с помощью Open Authorization или OAuth).</span><span class="sxs-lookup"><span data-stu-id="b93d4-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="b93d4-117">Темы планирования проверки подлинности и авторизации</span><span class="sxs-lookup"><span data-stu-id="b93d4-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="b93d4-118">Использование современной проверки подлинности (ADAL) в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b93d4-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="b93d4-119">Топологии Skype для бизнеса, поддерживаемые современной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="b93d4-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="b93d4-120">Планирование отключения устаревших методов проверки подлинности внутри сети и за ее внешними границами.</span><span class="sxs-lookup"><span data-stu-id="b93d4-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

