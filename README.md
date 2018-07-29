# coursera-r-assignment-2

## Put comments here that give an overall description of what your
## functions do

## This is Coursera R programming week 3 assignment done by rrober55

## This function creates a special "matrix" object that can cache its inverse.
makeCacheMatrix <- function(x = matrix()) {
	# Initialize the empty object
	inv <- NULL
	
	# Set Method
	# Get input matrix as "x"
	# Value of the inverse
	
	set <- function(y) {
	x <<- y
	inv <<- NULL

}
	# Get Method
	#Returns stored value for the matrix "x"
	get <- function() x
	
	# Set method
	# Set the value of the inverse matrix
	setInverse <- function(solveMatrix) inv <<- solveMatrix
	
	# Get Method
	# Get the value of the inverse matrix
	getInverse <- function () inv
	
	# Return a list of all methods
	list(set = set, get = get, setinverse = setinverse, getinverse = getinverse)
}

##  This function computes the inverse of the special "matrix" returned by makeCacheMatrix above. 
## If the inverse has already been calculated (and the matrix has not changed), 
## then the cachesolve should retrieve the inverse from the cache.

cacheSolve <- function(x, ...) {

        # Return a matrix that is the inverse of 'x'
	inv <- x$getInverse()
	
	# If the nverse has already been computed, return it
	if(!is.null(inv)){
	message("getting cached data")
	return(inv)
} 
	# Else, get the orginal matrix and solve it
	data <- x$get()
	inv <- solve(data)
	x$setInverse(inv)
	
	# Return the computed inverse
	inv
}
