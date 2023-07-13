# A-maZe
          newY < numCols &&
          maze[newX][newY] === 0 &&
          !visited[newX][newY]
        ) {
          const newPath = explore(newX, newY, path.concat([[x, y]]));
          if (newPath) {
            return newPath;
          }
        }
      }

      // No path found, backtrack
      return null;
    }

    // Start exploring the maze from the start coordinates
    const path = explore(startX, startY, []);

    if (path) {
      return path;
    } else {
      throw new Error("No path found");
    }
  } catch (error) {
    // Log the error
    console.error(error);
    return [];
  }
}
