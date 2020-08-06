---
title: Aprimorar o acesso aos dados de rastreamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679763"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="3094c-102">Aprimorar o acesso aos dados de rastreamento</span><span class="sxs-lookup"><span data-stu-id="3094c-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="3094c-103">usa o espaço no diretório **temp** para aprimorar o acesso aos dados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="3094c-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="3094c-104">exige, pelo menos, 10 MB (megabytes) de espaço livre.</span><span class="sxs-lookup"><span data-stu-id="3094c-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="3094c-105">Se o espaço livre cair abaixo de 10 MB enquanto você estiver usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], todas as funções do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] serão interrompidas.</span><span class="sxs-lookup"><span data-stu-id="3094c-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="3094c-106">Quando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] usar o espaço no diretório **temp** , este uso de espaço pode fazer o diretório **temp** crescer rapidamente.</span><span class="sxs-lookup"><span data-stu-id="3094c-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="3094c-107">Para evitar problemas com a expansão de arquivos, você pode colocar o diretório **temp** em uma unidade que não é unidade de sistema alterando o valor da variável de ambiente TEMP.</span><span class="sxs-lookup"><span data-stu-id="3094c-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="3094c-108">O procedimento a seguir descreve como alterar o valor da variável de ambiente TEMP na maioria dos sistemas operacionais Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3094c-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="3094c-109">Para obter mais informações sobre como definir variáveis de ambiente, consulte a documentação de seu sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="3094c-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="3094c-110">Para alterar a variável de ambiente TEMP em sistemas operacionais Windows</span><span class="sxs-lookup"><span data-stu-id="3094c-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="3094c-111">No menu **Iniciar** , escolha **Painel de Controle**e clique em **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="3094c-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="3094c-112">Na caixa de diálogo **Propriedades do Sistema** , clique na guia **Avançado** e clique em **Variáveis de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="3094c-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="3094c-113">Role para baixo a lista de **Variáveis do sistema**, selecione a linha que corresponde à variável **TEMP** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3094c-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="3094c-114">Na caixa de diálogo **Editar Variável do Sistema** , insira o caminho e o nome da unidade e diretório em que você deseja que o diretório **temp** esteja localizado.</span><span class="sxs-lookup"><span data-stu-id="3094c-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="3094c-115">Clique em **OK** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="3094c-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3094c-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3094c-116">See Also</span></span>  
 <span data-ttu-id="3094c-117">[Iniciar o SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="3094c-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="3094c-118">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3094c-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
