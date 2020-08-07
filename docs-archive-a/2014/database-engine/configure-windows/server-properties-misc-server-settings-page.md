---
title: Propriedades do servidor – página Configurações Diversas do Servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574899"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="15c51-102">Propriedades do servidor (página Diversas Configurações de Servidor)</span><span class="sxs-lookup"><span data-stu-id="15c51-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="15c51-103">Use esta página para exibir ou modificar as configurações de servidor.</span><span class="sxs-lookup"><span data-stu-id="15c51-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15c51-104">Opções</span><span class="sxs-lookup"><span data-stu-id="15c51-104">Options</span></span>  
 <span data-ttu-id="15c51-105">**Linguagem padrão para usuários**</span><span class="sxs-lookup"><span data-stu-id="15c51-105">**Default language for users**</span></span>  
 <span data-ttu-id="15c51-106">Especifica a linguagem padrão para todos os logons recém-criados.</span><span class="sxs-lookup"><span data-stu-id="15c51-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="15c51-107">**Permitir que gatilhos acionem outros gatilhos**</span><span class="sxs-lookup"><span data-stu-id="15c51-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="15c51-108">Controla se um gatilho pode executar uma ação que inicia outro gatilho.</span><span class="sxs-lookup"><span data-stu-id="15c51-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="15c51-109">Quando desmarcado, os gatilhos não podem ser acionados por outro gatilho.</span><span class="sxs-lookup"><span data-stu-id="15c51-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="15c51-110">Quando selecionado, os gatilhos podem ser acionados por outros gatilhos em até 32 níveis.</span><span class="sxs-lookup"><span data-stu-id="15c51-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="15c51-111">**Usar administrador de consultas para evitar consultas demoradas**</span><span class="sxs-lookup"><span data-stu-id="15c51-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="15c51-112">Especifica um limite superior de tempo em que uma consulta pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="15c51-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="15c51-113">O custo da consulta refere-se ao tempo decorrido estimado, em segundos, necessário para executar uma consulta em uma configuração de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="15c51-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="15c51-114">Por padrão, o administrador de consultas é desativado e todas as consultas têm permissão para serem executadas.</span><span class="sxs-lookup"><span data-stu-id="15c51-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="15c51-115">Se essa opção for selecionada, você deve digitar um limite de tempo na caixa de texto abaixo.</span><span class="sxs-lookup"><span data-stu-id="15c51-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="15c51-116">Se você especificar um valor que não seja zero nem negativo, o administrador de consultas recusará a execução de qualquer consulta com um custo estimado que exceda aquele valor.</span><span class="sxs-lookup"><span data-stu-id="15c51-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="15c51-117">**Interpretar um ano de dois dígitos como incluído entre**</span><span class="sxs-lookup"><span data-stu-id="15c51-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="15c51-118">Especifica o intervalo de datas de 100 anos para interpretar valores de anos com dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="15c51-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> <span data-ttu-id="15c51-119">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpretará valores de datas de dois dígitos como referências ao final do ano com esses dígitos e que se inclui no intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="15c51-119">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="15c51-120">Define a caixa à direita com o ano final.</span><span class="sxs-lookup"><span data-stu-id="15c51-120">Set the right box with the ending year.</span></span> <span data-ttu-id="15c51-121">Quando o ano final for salvo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populará automaticamente a caixa com o ano inicial.</span><span class="sxs-lookup"><span data-stu-id="15c51-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="15c51-122">**Valores Configurados**</span><span class="sxs-lookup"><span data-stu-id="15c51-122">**Configured Values**</span></span>  
 <span data-ttu-id="15c51-123">Exibe os valores configurados para as opções nesse painel.</span><span class="sxs-lookup"><span data-stu-id="15c51-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="15c51-124">Se você alterar esses valores, clique em **Executando Valores** para verificar se as alterações entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="15c51-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="15c51-125">Se as alterações não entraram em vigor, a instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deverá ser redeclarada primeiro.</span><span class="sxs-lookup"><span data-stu-id="15c51-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="15c51-126">**Executando Valores**</span><span class="sxs-lookup"><span data-stu-id="15c51-126">**Running Values**</span></span>  
 <span data-ttu-id="15c51-127">Exiba os valores que estão sendo executados para as opções neste painel.</span><span class="sxs-lookup"><span data-stu-id="15c51-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="15c51-128">Esses valores são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="15c51-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c51-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15c51-129">See Also</span></span>  
 [<span data-ttu-id="15c51-130">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="15c51-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
