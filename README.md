# coursera-r-assignment-2

## Put comments here that give an overall description of what your
## functions do

## This is Coursera R programming week 3 assignment done by rrober55

## This function creates a special "matrix" object that can cache its inverse.
makeCacheMatrix <- function(x = matrix()) {
	inv <- NULL									# Initialize the empty object
	set <- function(y) {								# Set Method
		x <<- y									# Get input matrix as "x"
		inv <<- NULL								# Value of the inverse

}
	
	get <- function() x								# Get Method
											# Returns stored value for the matrix "x"
	
	setinv <- function(invers) inv <<- invers					# Set method
											# Set the value of the inverse matrix
	
	getinv <- function () inv							# Get Method
											# Get the value of the inverse matrix
	
	# Return a list of all methods
	list(set = set, get = get, setinv = setinv, getinv = getinv)			# Return a list of all methods
}

##  This function computes the inverse of the special "matrix" returned by makeCacheMatrix above. 
## If the inverse has already been calculated (and the matrix has not changed), 
## then the cachesolve should retrieve the inverse from the cache.

cacheSolve <- function(x, ...) {

	inv <- x$getinv()								  # Return a matrix that is the inverse of 'x'
	
	if(!is.null(inv)){								  # If the nverse has already been computed, 													return it						message("getting cached data")
		return(inv)
} 
	data <- x$get()									 # Else, get the orginal matrix and solve it		inv <- solve(data)
	x$setinv(inv)
	
	inv										 # Return the computed inverse
}
