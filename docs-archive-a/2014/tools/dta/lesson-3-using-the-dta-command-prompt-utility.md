---
title: 'Lição 3: Como usar o utilitário de Prompt de comando dta | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678436"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="c9037-102">Lição 3: Usando o utilitário de prompt de comando dta</span><span class="sxs-lookup"><span data-stu-id="c9037-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="c9037-103">O utilitário de prompt de comando **dta** oferece funcionalidade além da fornecida pelo Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9037-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="c9037-104">Você pode usar suas ferramentas XML favoritas para criar arquivos de entrada para o utilitário usando o esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9037-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="c9037-105">Esse esquema é instalado durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e pode ser encontrado em: C:\Arquivos de Programas (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="c9037-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="c9037-106">O esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados também está disponível online no [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="c9037-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="c9037-107">O esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados oferece mais flexibilidade para definir opções de ajuste.</span><span class="sxs-lookup"><span data-stu-id="c9037-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="c9037-108">Ele permite, por exemplo, executar a análise hipotética.</span><span class="sxs-lookup"><span data-stu-id="c9037-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="c9037-109">A análise hipotética compreende a especificação de um conjunto de estruturas de design físicas hipotéticas e existentes para o banco de dados a ser ajustado e a análise usando o Orientador de Otimização do Mecanismo de Banco de Dados para descobrir se esse design físico hipotético melhorará o desempenho do processamento de consulta.</span><span class="sxs-lookup"><span data-stu-id="c9037-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="c9037-110">Esse tipo de análise oferece a vantagem de poder avaliar a nova configuração sem incorrer na sobrecarga da implementação de fato.</span><span class="sxs-lookup"><span data-stu-id="c9037-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="c9037-111">Se seu design físico hipotético não oferecer a melhora de desempenho desejada, é fácil alterá-lo e fazer novas análises até que você alcance a configuração que produza os resultados necessários.</span><span class="sxs-lookup"><span data-stu-id="c9037-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="c9037-112">Além disso, usando o esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados e o utilitário de prompt de comando **dta** , você pode inserir a funcionalidade do Orientador de Otimização do Mecanismo de Banco de Dados em scripts e usá-la com outras ferramentas de design de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c9037-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="c9037-113">A utilização da funcionalidade de entrada XML do Orientador de Otimização do Mecanismo de Banco de Dados ultrapassa o alcance desta lição.</span><span class="sxs-lookup"><span data-stu-id="c9037-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="c9037-114">Esta lição fornece uma introdução à sintaxe básica do utilitário de prompt de comando **dta** , como acessar a ajuda e à prática do ajuste de cargas de trabalho simples.</span><span class="sxs-lookup"><span data-stu-id="c9037-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="c9037-115">Ela contém o seguinte tópico:</span><span class="sxs-lookup"><span data-stu-id="c9037-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="c9037-116">Iniciando o utilitário de prompt de comando **DTA** e ajustando uma carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9037-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c9037-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="c9037-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c9037-118">Iniciando o utilitário de prompt de comando dta e ajustando uma carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9037-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
