---
title: Assistente de compilação nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685678"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="636c7-102">Orientador de compilação nativa</span><span class="sxs-lookup"><span data-stu-id="636c7-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="636c7-103">A ferramenta de relatórios de desempenho da transação (consulte [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informa sobre quais procedimentos armazenados interpretados no banco de dados serão beneficiados se usarem a compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="636c7-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="636c7-104">Depois de identificar um procedimento armazenado que você gostaria de ser aprovado para usar a compilação nativa, você poderá usar o orientador de compilação nativa para ajudá-lo a migrar o procedimento armazenado interpretado para compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="636c7-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="636c7-105">Para obter mais informações sobre procedimentos armazenados nativamente compilados, consulte [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="636c7-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="636c7-106">Para começar, conecte-se à instância que contém o procedimento armazenado interpretado.</span><span class="sxs-lookup"><span data-stu-id="636c7-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="636c7-107">Você pode se conectar a uma instância do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]ou [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="636c7-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="636c7-108">No entanto, se você desejar executar uma operação de migração com o orientador, deverá se conectar a uma instância do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] na qual a funcionalidade de OLTP na memória está habilitada.</span><span class="sxs-lookup"><span data-stu-id="636c7-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="636c7-109">Para obter mais informações sobre os requisitos de OLTP na memória, consulte [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="636c7-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="636c7-110">Para obter informações sobre as metodologias de migração, confira [In-Memory OLTP – Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx)(OLTP in-memory – Padrões comuns de carga de trabalho e considerações de migração).</span><span class="sxs-lookup"><span data-stu-id="636c7-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="636c7-111">Passo a passo usando o orientador de compilação nativa</span><span class="sxs-lookup"><span data-stu-id="636c7-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="636c7-112">No **Pesquisador de Objetos**, clique com o botão direito do mouse no procedimento armazenado que você quer converter e selecione **Orientador de Compilação Nativa**.</span><span class="sxs-lookup"><span data-stu-id="636c7-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="636c7-113">Isso exibirá a página de boas-vindas para o **Orientador de Compilação Nativa de Procedimento Armazenado**.</span><span class="sxs-lookup"><span data-stu-id="636c7-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="636c7-114">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="636c7-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="636c7-115">Validação de procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="636c7-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="636c7-116">Essa página relatará se o procedimento armazenado usar alguma construção que não seja compatível com compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="636c7-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="636c7-117">Você pode clicar em **Avançar** para ver detalhes.</span><span class="sxs-lookup"><span data-stu-id="636c7-117">You can click **Next** to see details.</span></span> <span data-ttu-id="636c7-118">Se houver construções que não sejam compatíveis com compilação nativa, você poderá clicar em **Avançar** para ver detalhes.</span><span class="sxs-lookup"><span data-stu-id="636c7-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="636c7-119">Resultado de validação de procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="636c7-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="636c7-120">Se houver construções que não sejam compatíveis com compilação nativa, a página **Resultado de Validação de Procedimento Armazenado** exibirá detalhes.</span><span class="sxs-lookup"><span data-stu-id="636c7-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="636c7-121">Você pode gerar um relatório (clique em **Gerar Relatório**), saia do **Supervisor de Compilação Nativa**e atualize seu código de forma que seja compatível com a compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="636c7-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="636c7-122">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="636c7-122">Code Sample</span></span>  
 <span data-ttu-id="636c7-123">O exemplo a seguir mostra um procedimento armazenado interpretado e o procedimento armazenado equivalente para compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="636c7-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="636c7-124">O exemplo supõe um diretório chamado c:\data.</span><span class="sxs-lookup"><span data-stu-id="636c7-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="636c7-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="636c7-125">See Also</span></span>  
 [<span data-ttu-id="636c7-126">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="636c7-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
