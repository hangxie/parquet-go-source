This repo will be archived, I've rewrite the history to make all codes under source/ (https://github.com/hangxie/parquet-go-source/tree/hangxie/merge) then merge this repo to https://github.com/hangxie/parquet-go, more details can be found at https://github.com/hangxie/parquet-go/pull/17.

# parquet-go-source 

parquet-go-source is a source provider for parquet-go. Your source must implement ParquetFile interface:

```go
type ParquetFile interface {
	io.Seeker
	io.Reader
	io.Writer
	io.Closer
	Open(name string) (ParquetFile, error)
	Create(name string) (ParquetFile, error)
}
```

Now it supports:
* Local
* HDFS
* S3 (by [shsing2000](https://github.com/shsing2000))
* GCS (by [AOHUA](https://github.com/AOHUA))
* MemoryFileSystem (by [daikokoro](https://github.com/daidokoro))
* MemoryBuffer (by [pmalekn](https://github.com/pmalekn))
* HTTP Multipart Request Body (by [mcgrawia](https://github.com/mcgrawia))
* Azure Blobs (by [davigust](https://github.com/davigust))

Thanks for all the contributors !
