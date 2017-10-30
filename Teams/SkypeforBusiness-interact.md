---
title: "Взаимодействие Skype для бизнеса и Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Сведения о взаимодействии Skype для бизнеса и Microsoft Teams в рамках чатов и звонков."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="9b0c7-103">Взаимодействие Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b0c7-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="9b0c7-104">Если сейчас ваша организация использует Skype для бизнеса, важно понять, как именно этот продукт будет взаимодействовать с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="9b0c7-105">После выпуска общедоступной версии Microsoft Teams базовое взаимодействие между этим продуктом и Skype для бизнеса Online или соответствующей гибридной средой будет доступно только для однорангового обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="9b0c7-106">По умолчанию клиент Microsoft Teams входит как в серверные службы Microsoft Teams, так и в службы Skype для бизнеса (подход с двойным стеком).</span><span class="sxs-lookup"><span data-stu-id="9b0c7-106">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach).</span></span> <span data-ttu-id="9b0c7-107">Клиент Microsoft Teams предоставит функции обмена мгновенными сообщениями только Skype для бизнеса, поэтому при поиске пользователя Microsoft Teams из Skype для бизнеса он будет иметь пометку "Только мгновенные сообщения". В примере ниже пользователь Alix Wilber вошел только в клиент Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-107">The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="9b0c7-108">В Microsoft Teams можно искать пользователей своей организации, у которых активен Skype для бизнеса, и обмениваться с ними мгновенными сообщениями в сеансах чата.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="9b0c7-109">Пользователи Skype для бизнеса могут отвечать на такие сообщения, при этом ответы отображаются в окне чата Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="9b0c7-110">Пользователи Microsoft Teams, если для них также включена поддержка Skype для бизнеса, могут одновременно войти в Microsoft Teams и Skype для бизнеса с помощью соответствующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="9b0c7-111">Учитывается последняя активная конечная точка. Поэтому если пользователь работает с Microsoft Teams, мгновенные сообщения от пользователя Skype для бизнеса отображаются в окне чата Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-111">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window.</span></span> <span data-ttu-id="9b0c7-112">Если сотрудник использует Skype для бизнеса для выполнения или приема звонков либо только что закончил разговор в этом продукте и не вернулся в клиент Microsoft Teams, входящие мгновенные сообщения от пользователя Skype для бизнеса отображаются в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-112">If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="9b0c7-113">Так как сейчас Microsoft Teams поддерживает взаимодействие со Skype для бизнеса только в рамках однорангового обмена мгновенными сообщениями, все голосовые и видеозвонки, а также приглашения на собрания Skype для бизнеса любых модальностей от других пользователей Skype для бизнеса направляются только в клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-113">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only.</span></span> <span data-ttu-id="9b0c7-114">И наоборот, все голосовые и видеозвонки, а также приглашения присоединиться к групповому звонку любых модальностей из клиента Microsoft Teams направляются только в клиент Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-114">In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="9b0c7-115">Подобное поведение обеспечивает комфортное параллельное использование Microsoft Teams и Skype для бизнеса и позволяет выбирать подходящее средство под конкретные задачи.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-115">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool.</span></span> <span data-ttu-id="9b0c7-116">Однако может потребоваться проинформировать конечных пользователей об этих особенностях, чтобы они понимали, как осуществляется взаимодействие и как это способно повлиять на работу.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-116">However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="9b0c7-117">Примечание.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-117">Note:</span></span></br>      |<span data-ttu-id="9b0c7-118">При использовании Skype для бизнеса мгновенные сообщения, отправляемые в Teams, не регистрируются в журнале бесед Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="9b0c7-119">Microsoft Teams позволяет пользователям отключить взаимодействие со Skype для бизнеса в параметрах уведомлений.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-119">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings.</span></span> <span data-ttu-id="9b0c7-120">Эта функция управляется пользователем, чтобы каждый из сотрудников мог выбрать подходящий ему режим работы.</span><span class="sxs-lookup"><span data-stu-id="9b0c7-120">This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
