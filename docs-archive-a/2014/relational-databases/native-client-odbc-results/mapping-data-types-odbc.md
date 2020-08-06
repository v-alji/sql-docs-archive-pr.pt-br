---
title: Mapeando tipos de dados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685633"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="a20b1-102">Mapeando tipos de dados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a20b1-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="a20b1-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client mapeia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados SQL para tipos de dados SQL ODBC.</span><span class="sxs-lookup"><span data-stu-id="a20b1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="a20b1-104">As seções a seguir abordam os tipos de dados SQL do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e os tipos de dados SQL ODBC para os quais é feito o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="a20b1-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="a20b1-105">Também são abordados os tipos de dados SQL ODBC e seus tipos de dados C ODBC correspondentes, além das conversões padrão e as com suporte.</span><span class="sxs-lookup"><span data-stu-id="a20b1-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a20b1-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de dados **timestamp** é mapeado para o tipo de dados SQL_BINARY ou SQL_VARBINARY ODBC porque os valores nas colunas **timestamp** não são valores **DateTime** , mas valores **binários (8)** ou **varbinary (8)** que indicam a sequência de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atividade na linha.</span><span class="sxs-lookup"><span data-stu-id="a20b1-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="a20b1-107">Se o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client encontrar um valor SQL_C_WCHAR (Unicode) que tenha um número ímpar de bytes, o byte ímpar à direita será truncado.</span><span class="sxs-lookup"><span data-stu-id="a20b1-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="a20b1-108">Lidando com o tipo de dados sql_variant no ODBC</span><span class="sxs-lookup"><span data-stu-id="a20b1-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="a20b1-109">A coluna de tipo de dados **sql_variant** pode conter qualquer um dos tipos de dados em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto objetos grandes (LOBs), como **Text**, **ntext**e **Image**.</span><span class="sxs-lookup"><span data-stu-id="a20b1-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="a20b1-110">Por exemplo, a coluna pode conter valores **smallint** para algumas linhas, valores **flutuantes** para outras linhas e valores **Char/nchar** no restante.</span><span class="sxs-lookup"><span data-stu-id="a20b1-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="a20b1-111">O tipo de dados **sql_variant** é semelhante ao tipo de dados **variant** no Microsoft Visual Basic??.</span><span class="sxs-lookup"><span data-stu-id="a20b1-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="a20b1-112">Recuperando dados do servidor</span><span class="sxs-lookup"><span data-stu-id="a20b1-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="a20b1-113">O ODBC não tem um conceito de tipos variantes, limitando o uso do tipo de dados **sql_variant** com um driver ODBC no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a20b1-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a20b1-114">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se a associação for especificada, o tipo de dados **sql_variant** deverá ser associado a um dos tipos de dados ODBC documentados.</span><span class="sxs-lookup"><span data-stu-id="a20b1-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="a20b1-115">**SQL_CA_SS_VARIANT_TYPE**, um novo atributo específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client, retorna o tipo de dados de uma instância na coluna **sql_variant** ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a20b1-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="a20b1-116">Se nenhuma associação for especificada, a função [SQLGetData](../native-client-odbc-api/sqlgetdata.md) poderá ser usada para determinar o tipo de dados de uma instância na coluna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="a20b1-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="a20b1-117">Para recuperar **sql_variant** dados, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a20b1-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="a20b1-118">Chame **SQLFetch** para posicionar para a linha recuperada.</span><span class="sxs-lookup"><span data-stu-id="a20b1-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="a20b1-119">Chame **SQLGetData**, especificando SQL_C_BINARY para o tipo e 0 para o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="a20b1-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="a20b1-120">Isso força o driver a ler o cabeçalho de **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="a20b1-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="a20b1-121">O cabeçalho fornece o tipo de dados dessa instância na coluna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="a20b1-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="a20b1-122">**SQLGetData** retorna o tamanho (em bytes) do valor.</span><span class="sxs-lookup"><span data-stu-id="a20b1-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="a20b1-123">Chame [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) especificando **SQL_CA_SS_VARIANT_TYPE** como seu valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="a20b1-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="a20b1-124">Essa função retornará o tipo de dados C da instância na coluna **sql_variant** para o cliente.</span><span class="sxs-lookup"><span data-stu-id="a20b1-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="a20b1-125">Aqui está um segmento de código que ilustra as etapas acima.</span><span class="sxs-lookup"><span data-stu-id="a20b1-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="a20b1-126">Se o usuário criar a Associação usando [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), o driver lerá os metadados e os dados.</span><span class="sxs-lookup"><span data-stu-id="a20b1-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="a20b1-127">O driver converte os dados no tipo ODBC apropriado especificado na associação.</span><span class="sxs-lookup"><span data-stu-id="a20b1-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="a20b1-128">Enviando dados ao servidor</span><span class="sxs-lookup"><span data-stu-id="a20b1-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="a20b1-129">**SQL_SS_VARIANT**, um novo tipo de dados específico para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client, é usado para os dados enviados a uma coluna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="a20b1-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="a20b1-130">Ao enviar dados para o servidor usando parâmetros (por exemplo, inserir em valores de TableName (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) é usado para especificar as informações de parâmetro, incluindo o tipo C e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo correspondente.</span><span class="sxs-lookup"><span data-stu-id="a20b1-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="a20b1-131">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client converterá o tipo de dados C em um dos subtipos de **sql_variant** apropriados.</span><span class="sxs-lookup"><span data-stu-id="a20b1-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20b1-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a20b1-132">See Also</span></span>  
 [<span data-ttu-id="a20b1-133">Processando resultados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a20b1-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
