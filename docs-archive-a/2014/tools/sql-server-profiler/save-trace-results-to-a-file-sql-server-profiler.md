---
title: Salvar resultados de rastreamento em um arquivo (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683827"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="cb205-102">Salvar resultados de rastreamento em um arquivo (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="cb205-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="cb205-103">Este tópico descreve como salvar resultados de rastreamento em um arquivo, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb205-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="cb205-104">Para salvar resultados de rastreamento em um arquivo</span><span class="sxs-lookup"><span data-stu-id="cb205-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="cb205-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb205-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="cb205-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="cb205-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb205-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="cb205-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="cb205-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="cb205-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="cb205-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cb205-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="cb205-110">Marque a caixa de seleção **Salvar em arquivo** .</span><span class="sxs-lookup"><span data-stu-id="cb205-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="cb205-111">A caixa de diálogo **Salvar Como**é exibida.</span><span class="sxs-lookup"><span data-stu-id="cb205-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="cb205-112">Especifique um caminho e um nome de arquivo, na caixa de diálogo **Salvar Como**.</span><span class="sxs-lookup"><span data-stu-id="cb205-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="cb205-113">Clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="cb205-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb205-114">Certifique-se de que o serviço do SQL Server tenha permissões adequadas para gravação em arquivo no diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="cb205-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="cb205-115">Na caixa de diálogo **Propriedades do Rastreamento** , insira o tamanho do arquivo máximo na caixa de texto **Definir tamanho máximo do arquivo (MB)** .</span><span class="sxs-lookup"><span data-stu-id="cb205-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="cb205-116">O valor padrão é 5 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="cb205-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="cb205-117">Opcionalmente, especifique as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="cb205-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="cb205-118">Marque a caixa de seleção **Habilitar substituição de arquivo** para que o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] crie novos arquivos para rastreamento de dados quando o tamanho máximo for atingido.</span><span class="sxs-lookup"><span data-stu-id="cb205-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="cb205-119">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="cb205-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="cb205-120">Marque a caixa de seleção **Dados de rastreamento de processos do servidor** para assegurar que o servidor registre cada evento de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cb205-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cb205-121">Quando a opção **Dados de rastreamento de processos do servidor**está desmarcada, o servidor não registrará eventos caso eles degradem significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="cb205-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb205-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb205-122">See Also</span></span>  
 [<span data-ttu-id="cb205-123">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="cb205-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
