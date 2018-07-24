---
title: Настройка собрания страницы присоединения к в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Сводка: Сведения о настройке собрания страницы присоединения к в Скайп для Business Server.'
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977616"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="67fdb-103">Настройка собрания страницы присоединения к в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="67fdb-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="67fdb-104">**Сводка:** Сведения о настройке собрания страницы присоединения к в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="67fdb-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="67fdb-105">Когда пользователь щелкает ссылку собрания в приглашении на собрание, собрание страницы присоединения к определяет, будет ли Скайп для клиента Business уже установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="67fdb-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="67fdb-106">Если клиент уже установлен, клиент открывает и присоединился к собранию.</span><span class="sxs-lookup"><span data-stu-id="67fdb-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="67fdb-107">Если клиент не установлен, по умолчанию Скайп для бизнеса откроется клиента.</span><span class="sxs-lookup"><span data-stu-id="67fdb-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="67fdb-108">Настройка собрания страницы присоединения к</span><span class="sxs-lookup"><span data-stu-id="67fdb-108">Configure the meeting join page</span></span>

<span data-ttu-id="67fdb-109">Можно изменить поведение присоединения к собранию страницы, чтобы разрешить пользователям присоединяться к собраниям с других версий клиента.</span><span class="sxs-lookup"><span data-stu-id="67fdb-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="67fdb-110">Эти параметры конфигурации были удалены из Скайп для панели управления Business Server, но их настройка с помощью командлета Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="67fdb-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="67fdb-111">**Присоединение к Set-CsWebServiceConfiguration для страницы параметры собрания**</span><span class="sxs-lookup"><span data-stu-id="67fdb-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="67fdb-112">**Параметр SET-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="67fdb-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="67fdb-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="67fdb-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67fdb-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="67fdb-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="67fdb-115">Этот параметр устарел для использования с локальной версией Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="67fdb-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="67fdb-116">Если установлено значение True, присоединение к собранию с помощью клиентского приложения, отличный от Скайп для бизнеса будет предлагаться возможность присоединения к собранию с помощью их текущей клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="67fdb-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="67fdb-117">По умолчанию используется значение False.</span><span class="sxs-lookup"><span data-stu-id="67fdb-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="67fdb-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="67fdb-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="67fdb-119">Этот параметр устарел для использования с локальной версией Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="67fdb-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="67fdb-120">Если задано значение True, альтернативные параметры для присоединения к конференции в режиме online автоматически расширяется и отображается для пользователей.</span><span class="sxs-lookup"><span data-stu-id="67fdb-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="67fdb-121">Если задано значение False (значение по умолчанию), эти параметры будут доступны, но пользователь будет иметь для отображения списка параметров для себя.</span><span class="sxs-lookup"><span data-stu-id="67fdb-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

